# Trick Go to Help Check Your Interface

I've completely forgotten about this trick until today. At first it
doesn't look like anything relevant, even wasteful. But it forces the Go
compiler to be sure that your struct fulfills the interfaces. The `_`
ensures that none of this ever makes it into runtime, so there is no
performance loss for it.


```go
type Blah struct{}

// force compile-time check for fulfillment of interface
var _ fmt.Stringer = new(Blah)
var _ fmt.GoStringer = new(Blah)
```

    #golang #tips #interfaces
