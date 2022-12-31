# The Go `unicode` lookup tables are not safe for concurrency

This surprised me. The entire `unicode` package uses simple Go maps without any concurrency assurance. That means calling something as innocuous as `unicode.IsPrint` requires some sort of assurance of concurrency outside itself.

```go
// Categories is the set of Unicode category tables.
var Categories = map[string]*RangeTable{
  "C":  C,
  "Cc": Cc,
  "Cf": Cf,
}
```

People mistakenly think reading from `map` is safe for concurrency, but there is a lot of information written about why that is absolutely *not* safe. In fact, running with `-race` on will prove it. The reason is that the underlying hashing algorithm optimizes the most frequently read keys from the map and that is an (internal) write operation.

The only way to get safe `map` interactions is by wrapping with a semaphore, using `sync.Map`, or another channeled read approach. This was by design to keep Go raw `map` types wicked fast, and, I presume, is the reason that Rob Pike decided to keep the `unicode` lookup tables as fast as possible by not imposing concurrency protection prematurely.

I'm really glad I noticed this because I was adding premature concurrency safety assurance to my PEG packrat parser that would have been a *huge* performance hit for most applications without being needed. 
