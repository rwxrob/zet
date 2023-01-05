# Going with `Check` over `Parse` or `Match`

Since the primary artifact produces from `rat` is a `Result` makes sense to use the verb `Check` over the other traditional ones that are associated with regular expressions. Match implies just a scan for a surface match. Go has `Find` to return results (which I have always found a bit off).

Another reason to use `Check` is to emphasize that there is no parsing going on, just bookmarking pointers to positions in the underlying memory of the `[]rune` slice. Then, later people can pull out of it what they want without consuming the memory wastefully and dedicating it to sub-slices.
