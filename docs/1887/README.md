# Use structs for type switching in Go

One of the things that makes Go supremely better than all other languages for practical applications is its absolutely genius type system. Now that Go has generics its even better. Developers can encapsulate *anything* in a struct with a nameless field and just extract the value after the type switch or assertion. This technique is simply not possible in any other language (of which I'm aware).

```go
package main

import "fmt"

type Foo struct{ any }
type Bar struct{ any }

func DoSomething(it any) {

	switch v := it.(type) {

	case Foo:
		fmt.Printf("Do %T stuff to %p\n", v, v.any)

	case Bar:
		fmt.Printf("Do %T stuff to %p\n", v, v.any)
	}

}

func main() {
	same := &[]string{`one`}
	foo := Foo{same}
	bar := Bar{same}
	DoSomething(foo)
	DoSomething(bar)
}
```

Notice that the type is different even though the encapsulated `any` is pointing to the same underlying memory.

```out
Do main.Foo stuff to 0xc00000c030
Do main.Bar stuff to 0xc00000c030
```
