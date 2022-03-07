# Use `log` in Go Tests

It wasn't until recently that I discovered that `log.Print()` and
cousins are completely usable from within every possible Go test case.
All you have to do is change the `log` output to `os.Stdout` temporarily
and turn off the `log.Flags` so that get consistent output:

```go
func ExampleStack_invalid_JSON_Types() {
	defer log.SetOutput(os.Stderr)
	defer log.SetFlags(log.Flags())
	log.SetOutput(os.Stdout)
	log.SetFlags(0)
  log.Print("something")
  // Output:
  // something 
}
```

    #golang #coding #tips #log #testing #debugging
