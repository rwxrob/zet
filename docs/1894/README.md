# Pass Go maps as-is (`mymap`), slices by pointer (`&myslice`)

I keep forgetting that maps are like interfaces in Go, but not slices. You don't need to dereference a map at all. But you *do* need to dereference a slice if you want to make changes to it's underlying array.

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

And for slices...

```go
package main

import "fmt"

func BorkUpdate(a []string) {
	a = append(a, `some`)
}

func Update(a *[]string) {
  (*a) = append((*a), `some`)
}

func main() {
	one := []string{`one`}
	fmt.Println(one)
	Update(one)
	fmt.Println(one)

}
```

Produces:

```sh
$ go run /tmp/foo.go
[one]
[one]
[one some]
```
