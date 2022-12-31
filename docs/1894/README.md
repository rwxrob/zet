# Just pass maps (not pointers) in Go

I keep forgetting that maps are like interfaces in Go. You don't need to dereference them at all.

```go
package main

import "fmt"

type Loc struct {
	X int
	Y int
}

var Map = map[string]Loc{}

func Update(a map[string]Loc) {
	a[`some`] = Loc{3, 4}
}

func main() {

	fmt.Println(Map)
	Update(Map)
	fmt.Println(Map)

}
```

Produces:

```sh
$ go run /tmp/foo.go
map[]
map[some:{3 4}]
```
