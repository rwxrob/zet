# Just Check `slice == nil` Instead of `len(slice)`

Looks like `slice == nil` is a faster/easier check than checking the
length. But sometimes the length is needed.
