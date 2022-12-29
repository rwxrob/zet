# Use structs for type switching in Go

One of the things that makes Go supremely better than all other languages for practical applications is its absolutely genius type system. Now that Go has generics its even better. Developers can encapsulate *anything* in a struct with a nameless field and just extract the value after the type switch or assertion. This technique is simply not possible in any other language (of which I'm aware).

```go
type Foo struct { any }

```
