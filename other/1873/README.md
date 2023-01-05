# Get a Go function name through reflection (best effort)

There are some edge cases where this definitely does *not* work, and they are almost all when dealing with anonymous functions and closures.

```go
func funcName(it any) string {
	fp := reflect.ValueOf(it).Pointer()
	long := runtime.FuncForPC(fp).Name()
	parts := strings.Split(long, `.`)
	return parts[len(parts)-1]
}
```
