# Detect Platform in POSIX Shell

Sometimes it is useful to set detect difference between Linux, Mac, and
Windows. 

```sh
test -z "$OS" && export OS=$(uname)
case "$OS" in
Linux) export PLATFORM=linux ;;
*indows*) export PLATFORM=windows ;;
FreeBSD | Darwin) export PLATFORM=mac ;;
*) export PLATFORM=unknown ;;
esac
```
