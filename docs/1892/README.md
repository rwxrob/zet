# Go `unicode.RangeTables` maps are fast/safe for concurrent reads

This surprised me (as did discovering `map` reads are *always* safe for concurrency despite the sketchy language[^1]). The entire `unicode` package uses simple Go maps, which are *very* fast.

```go
// Categories is the set of Unicode category tables.
var Categories = map[string]*RangeTable{
  "C":  C,
  "Cc": Cc,
  "Cf": Cf,
}
```

[^1]: [Go maps are safe for concurrent reads (as best we can tell)](../1893)
