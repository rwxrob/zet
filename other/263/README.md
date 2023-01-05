# Remove `/var/apt/lists/*` in Container Images

This stuff doesn't need to be in the final image. Consider adding the
following near the end of your Dockerfile:

```sh
rm -rf /var/lib/apt/lists/*
```
