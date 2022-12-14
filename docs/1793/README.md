# Secure shell (`ssh`) required `-c` support

When I attempted to create a shell and call it from `ssh` client or `crypto/ssh.Session.Run` this is what gets dumped for `os.Args`. This means that the Secure Shell protocol itself requires that any shell supporting it automatically support the `-c` argument. This is also how `stdin` is freed up to be passed in after the fact.

```
$ ssh -i testdata/blahpriv blah@localhost "echo" <<< hello
2022/12/14 05:42:00 [safesh -c echo]

$ ssh -i testdata/blahpriv blah@localhost "ls -ld"
2022/12/14 05:45:39 [safesh -c ls -ld]

$ ssh -i testdata/blahpriv blah@localhost 'ls -la'
["safesh" "-c" "ls -la"]

$ ssh -i testdata/blahpriv blah@localhost ls -la
["safesh" "-c" "ls -la"]

$ ssh -i testdata/blahpriv blah@localhost ls -la -t -p
["safesh" "-c" "ls -la -t -p"]
```
