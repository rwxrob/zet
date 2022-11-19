# Potential Go Proposal for `fmt.Println`

The `fmt.Print*` family of functions are already very aware and magical
when it comes to printing things as strings --- particularly with the
`fmt.Stringer` interface. But what about bare stringer functions that
don't associate with a specific struct? Aren't they also things? After
all, we are talking first-class function support, no?

I propose we add the following as an acceptable argument type to
`fmt.Print*`:

```go
func() String
```
