# Notes and findings about goreleaser

The `goreleaser` tool allows easy go releases to be integrated with GitHub actions but has some dubious default settings including forcing dynamically-linked library dependencies (which are absolutely against the main advantage of statically-linked Go binaries).

## Installation and debugging recommendation

Since people doing the Go release likely have go installed just installing with Go seems to be the best option (of many):

```sh
go install github.com/goreleaser/goreleaser@latest
```

