# Caching ssh connections is 68 times faster than not

Caching the TCP/IP dial-up connection (`*ssh.Client`) is 67.72 times faster than recreating a new connection every time:

```
Uncached:   4059  88907623 ns/op  109533 B/op  570 allocs/op
Cached:   277924   1312706 ns/op   70661 B/op  145 allocs/op
```

```bc
scale=2; 88907623 / 1312706
```

```sh
go test -bench . -benchtime=5m -benchmem
goos: linux
goarch: amd64
pkg: github.com/rwxrob/ssh
cpu: Intel(R) Core(TM) i7-9700 CPU @ 3.00GHz
BenchmarkRun-8              4059          88907623 ns/op          109533 B/op        570 allocs/op
PASS
```

```sh
go test -bench . -benchtime=5m -benchmem
goos: linux
goarch: amd64
pkg: github.com/rwxrob/ssh
cpu: Intel(R) Core(TM) i7-9700 CPU @ 3.00GHz
BenchmarkRun-8            277924           1312706 ns/op           70661 B/op        145 allocs/op
PASS
```

Here's the benchmark code:

```go
package ssh_test

import (
	"fmt"
	"log"
	"os"
	"testing"
	"time"

	"github.com/rwxrob/ssh"
)

var ukey = `
-----BEGIN OPENSSH PRIVATE KEY-----
...
-----END OPENSSH PRIVATE KEY-----
`

func BenchmarkRun(b *testing.B) {
	for i := 0; i < b.N; i++ {
		stdout, stderr, err := ssh.Run(`user@localhost:22`, []byte(ukey), nil, `echo hi there`, ``)
		if err != nil || stdout != "hi there\n" || stderr != `` {
			log.Print(stdout)
			return
		}
	}
}
```

(Make sure not to use a private key that actually matters.)

The cache in this case is just a simple map with absolutely minimal closed connection recovery (which returns an error when creating a new Session).

```go
package ssh

import (
	"fmt"
	"log"
	"math/rand"
	"strings"
	"time"

	"golang.org/x/crypto/ssh"
)

// TCPTimeout is the default number of seconds to wait to complete a TCP
// connection.
var TCPTimeout = 300 * time.Second


var clients = map[string]*ssh.Client{}

// Run wraps the ssh.Session.Run command with sensible, stand-alone
// defaults. This function has no dependencies on any underlying ssh
// host installation making it idea for light-weight, remote ssh calls.
//
// Run combines several steps. First, a client secure shell connection
// is Dialed to the target (user@host:PORT) using the private key of the
// local user (ukey) and public host key in authorized_keys format (or nil
// to skip). Run then attempts to create a Session
// calling Run on it to execute the passed cmd feeding it any standard
// input (in) provided.  The standard output, standard error are then
// buffered and returned as strings. The exit value is captured in err
// for any exit code other than 0. See the ssh.Session.Run method for
// more information.
//
// Note that there are no limitations on the size of input and output
// meaning Run should only be used when calling remote commands that can
// be trusted not to produce too much output.
//
func Run(target string, ukey, hkey []byte, cmd, in string) (stdout, stderr string, err error) {

	t := strings.Split(target, "@")
	if len(t) != 2 {
		err = fmt.Errorf(`invalid target: %q`, target)
		return
	}
	user := t[0]
	addr := t[1]

	signer, err := ssh.ParsePrivateKey(ukey)
	if err != nil {
		return
	}

	var callback ssh.HostKeyCallback
	var hostkey, hostpub ssh.PublicKey

	if hkey != nil {

		hostkey, _, _, _, err = ssh.ParseAuthorizedKey(hkey)
		if err != nil {
			return
		}

		hostpub, err = ssh.ParsePublicKey(hostkey.Marshal())
		if err != nil {
			return
		}

		callback = ssh.FixedHostKey(hostpub)

	} else {

		callback = ssh.InsecureIgnoreHostKey()

	}

	var tried bool
	var client *ssh.Client

GETCLIENT:
	client, cached := clients[target]
	if !cached {
		client, err = ssh.Dial(`tcp`, addr, &ssh.ClientConfig{
			User:            user,
			Auth:            []ssh.AuthMethod{ssh.PublicKeys(signer)},
			HostKeyCallback: callback,
			Timeout:         TCPTimeout,
		})
		if err != nil {
			return
		}
		clients[target] = client
	}

	sess, err := client.NewSession()
	if sess != nil {
		defer sess.Close()
	}
	if err != nil {
		if !tried {
			delete(clients, target)
			tried = true
			goto GETCLIENT
		}
		return
	}

	if in != "" {
		sess.Stdin = strings.NewReader(in)
	}

	_out := new(strings.Builder)
	_err := new(strings.Builder)
	sess.Stdout = _out
	sess.Stderr = _err

	err = sess.Run(cmd)
	stdout = _out.String()
	stderr = _err.String()

	return

}

// ------------------------------- User -------------------------------

// we use an interface for flexibility and to allow the work to create
// a signer to only be needed once upon creation

type User struct {
	Name   string
	Key    []byte // original pemkey
	Signer ssh.Signer
}

func NewUser(name string, pemkey []byte) (*User, error) {
	var err error
	u := new(User)
	u.Name = name
	u.Key = pemkey
	u.Signer, err = ssh.ParsePrivateKey(pemkey)
	if err != nil {
		return u, err
	}
	return u, nil
}

// ------------------------------- Host -------------------------------

// we use an interface for flexibility and to allow the work to create
// a signer to only be needed once upon creation

type Host struct {
	Addr    string        // name or IP
	Auth    []byte        // authorized_hosts format
	Netkey  ssh.PublicKey // RFC 4235, section 6.6
	Pubkey  ssh.PublicKey // suitable for ssh.FixedHostkey
	Comment string        // authorized_hosts comment
	Options []string      // authorized_hosts options
	Client  *ssh.Client   // last (cached) client connection
}

func NewHost(addr string, authkey []byte) (*Host, error) {
	var err error
	host := new(Host)
	host.Addr = addr
	host.Auth = authkey

	if authkey == nil {
		return host, nil
	}

	host.Netkey, host.Comment, host.Options, _, err = ssh.ParseAuthorizedKey(authkey)
	if err != nil {
		return host, err
	}

	// required since host.net (also ssh.PublicKey) is in RFC format
	// (which fails for ssh.FixedHostKey)

	host.Pubkey, err = ssh.ParsePublicKey(host.Netkey.Marshal())
	if err != nil {
		return host, err
	}

	return host, nil
}

// -------------------------- MultiHostClient -------------------------

type MultiHostClient struct {
	User      *User         // user credentials to use
	Hosts     []*Host       // hosts to Dial
	Timeout   time.Duration // TCP/IP timeout (not session)
	Sleep     time.Duration // time to sleep between Dial calls
	Attempts  int           // number of attempts (0 same as 1)
	SafeDelim string        // RunSafe delimiter (default pkg SafeDelim)

	last int
}

func (c MultiHostClient) assert() {
	switch {
	case c.User == nil:
		panic(`undefined User`)
	case c.User.Name == "":
		panic(`undefined User.Name`)
	case c.User.Signer == nil:
		panic(`undefined User.Signer`)
	case c.Hosts == nil:
		panic(`undefined Hosts`)
	case c.Timeout == 0:
		panic(`Timeout cannot be 0`)
	case c.Attempts == 0:
		panic(`Attempts cannot be 0`)
	}
}

// Dial attempts to dial a random host from Hosts and rotates through
// all hosts until one responds or all hosts have been tried. Reuses a
// cached Host.Client if available to prevent creating new TCP/IP
// connections if not needed. The first host to respond to Dial is
// used.  Panics if any User, Hosts, Timeout, or Attempts is undefined.
func (c *MultiHostClient) Dial() (*ssh.Client, error) {
	c.assert()

	rand.Seed(time.Now().UnixNano())
	c.last = rand.Intn(len(c.Hosts))
	host := c.Hosts[c.last]

	var err error
	var client *ssh.Client
	var callback ssh.HostKeyCallback

	for n := 0; n < len(c.Hosts); n++ {

		if host.Auth == nil {
			callback = ssh.InsecureIgnoreHostKey()
		} else {
			callback = ssh.FixedHostKey(host.Pubkey)
		}

		client, err = ssh.Dial(`tcp`, host.Addr, &ssh.ClientConfig{
			User:            c.User.Name,
			Auth:            []ssh.AuthMethod{ssh.PublicKeys(c.User.Signer)},
			HostKeyCallback: callback,
			Timeout:         c.Timeout,
		})

		if err == nil {
			return client, nil
		}

		// error during dial
		log.Print(err)

		if c.last == len(c.Hosts)-1 {
			c.last = 0
		} else {
			c.last++
		}

		host = c.Hosts[c.last]
	}

	return nil, err

}

// DialUntil attempts to Dial Attempts number of times waiting in
// between for Sleep seconds in between each attempt.
func (c *MultiHostClient) DialUntil() (client *ssh.Client, err error) {
	n := 1
	for {
		client, err = c.Dial()
		if client != nil || n >= c.Attempts {
			break
		}
		n++
		time.Sleep(c.Sleep)
	}
	return
}

// Run gets a client connection with DialUntil and then runs the command
// (with optional stdin) as a Session on the remote host capturing the
// stdout, stderr as strings and returning the exit value in the error
// (see ssh.Session.Run). Note that no sanity checking is performed on
// the command passed and that most SSH servers will pass the cmd to the
// shell assigned to the remote user. This means that if semicolon where
// passed within the cmd string unexpected behavior could result.
// Therefore, it is critical that the cmd string passed be rigorously
// validated (usually through a very strict regular expression match) to
// prevent shell injection vulnerabilities. Another preventative
// measure is to provide a rudimentary shell for the remote user that
// disallows any shell expansion of any kind (effectively limiting all
// remote commands to their exec syscall equivalents).
func (c *MultiHostClient) Run(cmd, stdin string) (stdout, stderr string, err error) {

	client, err := c.DialUntil()
	if client == nil {
		err = fmt.Errorf(`failed to get client connection`)
		return
	}

	var sess *ssh.Session
	sess, err = client.NewSession()
	if err != nil {
		return
	}

	if stdin != "" {
		sess.Stdin = strings.NewReader(stdin)
	}

	_out := new(strings.Builder)
	_err := new(strings.Builder)
	sess.Stdout = _out
	sess.Stderr = _err

	err = sess.Run(cmd)
	stdout = _out.String()
	stderr = _err.String()

	return
}

func (c MultiHostClient) RunSafe(cmd string, args ...string) (stdout, stderr string, err error) {
	safelist := append([]string{cmd}, args...)
	if c.SafeDelim == "" {
		c.SafeDelim = SafeDelim
	}
	_cmd := strings.Join(safelist, c.SafeDelim)
	return c.Run(_cmd, ``)
}
```


