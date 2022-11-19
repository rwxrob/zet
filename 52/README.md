# Pointer for `MarshalJSON()`, None for `String()`

Just reminded that the `fmt.Stringer` interface demands a non-pointer as
the receiver while the `MarshalJSON` interface requires one. Mixing
these up can burn you in mysterious ways during testing.
