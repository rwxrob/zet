# I just (re)discovered anonymous/nameless fields in Go, and OMFG!

I've known for a long time about anonymous *structs* but had no idea there is a thing called anonymous fields.[^1] If a field doesn't have a name, then the *type* is used as the name.
It appears that only primitives work this way. An anonymous slice doesn't seem to work.

```go
package main

import "fmt"

type Foo struct {
	any
}

type Bar struct {
  any
  // []rune // breaks
}

func main() {
	same := &struct{ string }{`some`}
	foo := Foo{same}
	bar := Bar{same}
	fmt.Printf("%v (%[1]T) %v (%[2]T)\n", foo, bar)
	fmt.Printf("%v (%[1]T) %v (%[2]T)\n", foo.any, bar.any)
}
```

```out
{0xc000010250} (main.Foo) {0xc000010250} (main.Bar)
&{some} (*struct { string }) &{some} (*struct { string })
```

And you cannot use slices:

```out
# command-line-arguments
/tmp/foo.go:10:2: syntax error: unexpected [, expecting field name or embedded type
```

* Nameless fields in Go structs? - Stack Overflow  
  <https://stackoverflow.com/questions/28014591/nameless-fields-in-go-structs>
* Anonymous Structure and Field in Golang - GeeksforGeeks  
  <https://www.geeksforgeeks.org/anonymous-structure-and-field-in-golang/>

[^1]: The number of search hits that contain the word "anonymous" and "fields" that come back with boring explanations of anonymous structs (which are *not* the same as anonymous fields in a struct) is absolutely ridiculous. Almost nothing out there covers anonymous struct fields, so I don't feel so bad having read about them and completely obliterating them from my memory (and neither should you).
