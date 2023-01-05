# Never Use `foo == nil` Checks in Go for Interfaces

You can simply never trust something like the following, ever, to do the
right thing:

```go
func Some(foo FooInterface) {
  if foo != nil {
    fmt.Println("always true")
  }
}
```

This condition will always be true because the comparison to `nil` is
fucking brain-dead in Go. Both the type and the value have to match, and
they don't usually when working with interfaces in any way.

The *only* realistic option is to use lame-ass reflection:

```go
func Some(foo FooInterface) {
  if !reflect.ValueOf(foo).IsNil() {
    fmt.Println("always true")
  }
}
```

This is such a huge, stupid issue, that I've created a `check.Nil()` check
in `bonzai` to help me (and others) avoid this.

* Why Golang Nil Is Not Always Nil? Nil Explained
  <https://codefibershq.com/blog/golang-why-nil-is-not-always-nil>
* <https://developpaper.com/several-pits-based-on-go-interface-nil-and-their-principle-analysis/>
