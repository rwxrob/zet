# Returning slice of structs is faster than slice of pointers

It might not be intuitive, but the optimizations that are happening underneath actually make returning a slice of structs faster than a slice of pointers. Andrii Kushch has created a great benchmark to prove it:

    Benchmark_ReturnSliceWithPointers-8        10000
    186592 ns/op
    161920 B/op
    10001 allocs/opBenchmark_ReturnSliceWithStructs-8         10000
    11943 ns/op
    81920 B/op
    1 allocs/op

* Go: what to return? A slice of structs vs a slice of pointers? \| by Andrii Kushch \| Medium  
  https://andrii-kushch.medium.com/go-what-to-return-a-slice-of-structs-vs-a-slice-of-pointers-42647912530a
