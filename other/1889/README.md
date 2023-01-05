# Better to do type assertions in central `Pack` function

While writing `rat` I keep going back and forth about where to put the type assertions. It's the lazy programmer in me fighting the later lazy programmer in me using the thing. For example, which of the following to use to represent a literal:

```go
type Literal any
type Literal string
type Literal struct { any }
type Literal struct { string }
```

All of them work, but it's the last one that turns out to be the most efficient and best represented by the resulting syntax when creating grammars from `rat.Literal` types.

This means that the all the casting for the different variations of `Literal`
(`[]rune`, `[]byte`,`rune`) belongs in `Pack` and not the `String` and `Check`
functions where they would have to be otherwise (both of which are evaluated at
runtime causing an unnecessary performance hit). By promoting use of `Pack` for
such things we only go through that casting work once to create the grammar and
cache the resulting rules. This means a big type switch in `Pack` (which is
off-putting at first) but it is the *only* place that the casting happens
(which is well worth it).
