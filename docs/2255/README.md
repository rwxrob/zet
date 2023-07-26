# ChatGPT is brain-dead about Go interfaces

The following is directly against best practices from Essential Go that call for no `Get` for accessors (although `Set` is used for mutators).

```go
    type Host interface {
        // GetAddr returns the name or IP of the host.
        GetAddr() string

        // GetAuth returns the authorized_hosts format of the host.
        GetAuth() []byte

        // GetNetkey returns the RFC 4235, section 6.6 formatted public key of the host.
        GetNetkey() ssh.PublicKey

        // GetPubkey returns the public key suitable for ssh.FixedHostkey of the host.
        GetPubkey() ssh.PublicKey

        // GetComment returns the authorized_hosts comment of the host.
        GetComment() string

        // GetOptions returns the authorized_hosts options of the host.
        GetOptions() []string

        // GetClient returns the last (cached) client connection of the host.
        GetClient() *ssh.Client
    }
```
