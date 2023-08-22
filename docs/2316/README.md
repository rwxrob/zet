# Test for existence of a named, running container

```sh
name=ssh-server2
test -n "$(podman ps -q --filter "name=$name")" ; echo $?
```

Change `-n` to `-z` to test for the inverse.

