# Archlinux Container Bug Requires `--privileged`

Technically, it's not a bug. But you cannot `pacman -Sy` if you simply
run the `archlinux` container. You have to be sure to add `--privledged`
because even though your login and active/current user ID says `root`
apparently you aren't actually root.

```
docker run -it --privileged=true archlinux:latest bash
```

That's fucked up. But that's pretty much Arch Linux in a nutshell.
