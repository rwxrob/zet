# Use `T.Setenv` and `B.Setenv` When Go Testing

As of 1.17 using the `T.Setenv` method is var better than using
`os.Setenv` because it only lives during the scope of that test block.
