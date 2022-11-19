# Decrease Go Executable Size

Remove the symbol table and debugging information by adding `-ldflags`.

```
go build -ldflags="-s -w" ...
```

Should decrease by about 30%. Further shrinking requires compressors
that I just don't think are worth it.

    #golang #programming #optimizations
