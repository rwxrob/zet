# Check Go durations with regular comparison operators

Here's an example of a test to check that the time initialized on the returned structure was within two seconds of the time the test ran.

```go
func ExampleNewNode() {

	n := keg.NewNode()
	now := time.Now().UTC()

	fmt.Printf("ID: %q %v\n", n.ID(), n.Changed().Sub(now) < 2*time.Second)

	// Output:
	// ID: "-1" true

}
```
