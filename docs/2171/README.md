# Make sure to use full paths for `-v` volume mounts

Didn't work:

```
podman run -it --rm -v shared:/shared --hostname ca --name ca ghcr.io/rwxrob/ws-skilstak
```

Worked:

```
podman run -it --rm -v ~/shared:/shared --hostname ca --name ca ghcr.io/rwxrob/ws-skilstak
```

