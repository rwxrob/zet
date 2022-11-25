# Use `len(args)` Instead of `args == nil`

Using `nil` in comparisons that are not immediately obvious is always
dangerous. It's safer to use an explicit check of the length. That way
if it has been instantiated but has no values you still get the expected
behavior. There are many conditions where checking for `nil` equality
will fail but the slice won't have anything in it. An empty slice is sometimes *not* equivalent to `nil`.
