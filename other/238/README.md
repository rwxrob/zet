# Podman Works Flawlessly on Mac, Even Arm

The latest Podman encapsulated QEMU/KVM (like Docker Desktop but
better). It is absolutely amazing. The allows the fastest possible
time-to-linux command line possible from *any* laptop or workstation.

Mac

```
brew install podman
podman machine init --now
podman run -it --rm ubuntu
```


