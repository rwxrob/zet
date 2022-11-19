# Fix for podman buidah apt problems

```
apt update
apt remove buildah podman -y
apt autoremove -y
apt install buildah podman -y
```

