# Casting Anything to json.Object with Go Generics

```go
func ExampleObject_Print() {

	type FooBar struct {
		Foo string
		Bar string
	}

	json.Object{FooBar{"FOO", "BAR"}}.Print()

	// Output:
	// {"Foo":"FOO","Bar":"BAR"}
}
```

* <https://github.com/rwxrob/json>

    #golang #json #generics #tips
