# Use "reslicing" to clear array instead of creating new one in Go

This clears out the abstract slice that sits on top of the underlying allocated array in memory. Then, when reassigning new values that array is still there and doesn't need reallocation.

```go
allUsers = allUsers[:0]
```
