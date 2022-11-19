# Calling Function Instantiates Slices and Maps in Go

I've finally confirmed some behavior that I noticed the other day and
was very confused about. Go slices are abstractions that can be `nil`,
or empty (length zero) but when a slice is specified as a parameter to a
function that slice is *always* instantiated to some slice even if `nil`
is explicitly passed. This is definitely not intuitive, but it does mean
that you usually don't need to test a slice against `nil`. In fact,
passing nil will result in a check against nil being true, even though
the length is 0.

```golang
package main

import "fmt"

func testSlice(args []string) {
	if len(args) == 0 {
		fmt.Println("args length is zero")
	}
	if args == nil {
		fmt.Println("args value is nil")
	}
}

func testMap(args map[string]string) {
	if len(args) == 0 {
		fmt.Println("args length is zero")
	}
	if args == nil {
		fmt.Println("args value is nil")
	}
}

func main() {
	fmt.Println("======= testSlice(nil)")
	testSlice(nil)
	fmt.Println("======= testSlice([]string{})")
	testSlice([]string{})
	fmt.Println("======= testMap(nil)")
	testMap(nil)
	fmt.Println("======= testMap(map[string]string{})")
	testMap(map[string]string{})
}
```

Produces this unexpected output:

```out
======= testSlice(nil)
args length is zero
args value is nil
======= testSlice([]string{})
args length is zero
======= testMap(nil)
args length is zero
args value is nil
======= testMap(map[string]string{})
args length is zero
```

In both cases the length is zero, but the nil check is significantly
different.

The moral of the story is simple: use `len(args) == 0` to check for
missing arguments. It just works for everything, and no, it isn't slow,
the `len()` isn't actually a function call in Go.

    #golang #coding #tips
