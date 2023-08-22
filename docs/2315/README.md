# Fix rootless error with podman

Just installing `uidmap` was enough to fix this for some reason.

```sh
podman run -it --rm ubuntu
Error: command required for rootless mode with multiple IDs: exec: "newuidmap": executable file not found in $PATH
```

However, the `/usr/bin/newuidmap` file itself did not get installed initially and I had to do a `sudo apt reinstall uidmap` to get it to take.

