# 💀 Hack secure shell (`ssh`) with shell injection

Don't forget to validate your command input (DENY/ALLOW) before calling `ssh` in *any* form including from the excellent Go `crypto/ssh` package. Or, create an extremely limited shell for your remote account to which you will be remotely connecting. Here's why.

```sh
$ export DIR=';echo "would rm -rf"'
$ ssh blah@localhost -i testdata/blahpriv "ls -ld $DIR"
drwxr-x--- 5 blah blah 4096 Dec 10 03:03 .
would rm -rf
```
