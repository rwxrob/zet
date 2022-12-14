# Secure shell (`ssh`) required `-c` support

When I attempted to create a shell and call it from `ssh` client or `crypto/ssh.Session.Run` this is what gets dumped for `os.Args`. This means that the Secure Shell protocol itself requires that any shell supporting it automatically support the `-c` argument. This is also how `stdin` is freed up to be passed in after the fact.

```
2022/12/14 05:42:00 [safesh -c echo]
```
