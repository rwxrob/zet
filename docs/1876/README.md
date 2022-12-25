# PEG Packrat: "You don't need a fucking scanner"

Turns out the entire point of PEG packrat design approach is that you *don't need a rune scanner at all*. All the parse functions (functional) or blocks (virtual machine) just examine the same buffered memory data using positional pointers for the different rules. That's it.

In the case of functional design, you pass the pointer to the buffer (just a `[]rune` slice in Go) and the index pointing to the starting position for the rule function within that slice returning positional information and some way to indicate success or failure. Most return nil for failure, but I prefer setting a Result.Err instead.

```go
type Func(r []rune, i int) Result
```

Passing the starting position is unlike every other parsing approach I've ever known and leverages the PEG assumption of unlimited look-around and full memory loading to the fullest. Because you pass the starting position along with the actual data, *there is no for a scanner at all*.

I can't overstate how mind-blowing this was for me to fully comprehend. I already appreciated PEG (having made PEGN to build on it) but I had no idea how radically different the "parser" approaches are that it enables. I would never have dreamed a rune scanner was entirely unnecessary. Combined with Go slices and type switching (which no other language has built in by default), writing a packrat parser in Go might just be the best possible way to create one, period.

<https://github.com/rwxrob/rat>
