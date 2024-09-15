# Use `len(args)` Instead of `args == nil` in Go

Sunday, September 15, 2024,  6:38:15PM EDT

Reminded how valid this is. Perhaps one of the single biggest undocumented things about Go that everyone should know and do.

----

Using `nil` in comparisons that are not immediately obvious is always dangerous. It's safer to use an explicit check of the length. That way if it has been instantiated but has no values you still get the expected behavior. There are many conditions where checking for `nil` equality will fail but the slice won't have anything in it. An empty slice is sometimes *not* equivalent to `nil`.

All of this is because a slice is *not* an array as many have come to understand them. A slice is an abstraction that contains the following properties:

* A reference to the underlying, immutable array in memory
* Integer length (`len`)
* Integer array capacity (`cap`)

