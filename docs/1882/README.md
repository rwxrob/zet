# Stop repeating yourself with `fmt` in Go

By adding the bracketed argument position syntax to your `fmt` functions you only have to list the variable once. This is particularly useful when the type of the argument is wanted along with its value.

```go
    fmt.Sprintf("%v (%[1]T)\n", foo)
```
