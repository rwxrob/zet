# Use "preferred" Dockerfile ENTRYPOINT format

Found out the hard way that *not* using the "preferred" format for the `ENTRYPOINT` directive in Dockerfile just does completely odd things. Avoid it by just making use to use the "long" form.

```Dockerfile
ENTRYPOINT ["/entrypoint"]
```

(The one that works has the square brackets.)

* docs  
  <https://docs.docker.com/engine/reference/builder/#entrypoint>
