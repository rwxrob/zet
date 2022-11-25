# Create Custom Errors in Go with Interface

I feel a little embarrassed to learn that the `error` "primitive" in Go
isn't a primitive at all, it's an interface:

```go
type error interface {
  Error() string
}
```

That's all most Go programmers will need to know to realize everything
else that this means. Any struct that implements an Error() method and
usually an Unwrap() method can be encapsulated so that those trapping
the error can see what it was.

    #golang #coding #tips #errors
