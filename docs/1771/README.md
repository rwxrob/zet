# Only way to safely remove item from a slice (array) in Go

📺 <https://youtu.be/1_5GRcVS9DU>

The StackOverflow answers on this are ridiculously bad, but the discussion and understanding *why* they are so wrong is worth a look. Most of them are wrong because they would destroy any code that uses those methods with slices containing references to things that are being used by reference in other places in the same code base. Using references is one of the greatest things that Go supports (and why Rust is shit, you can't even implement a linked list in it without enabling "unsafe"). But all this Go awesomeness (which it gets from being like C in that regard) is completely thrown out the window if you do not preserve those references in the slices you are trying to shrink by some amount removing items in the list. The *only* way to do this properly is build a *new* slice containing exactly what was in the other, with a brand new underlying array to go with the slice.

By the way, this is one of those times when Go generics become obviously needed. This code wouldn't be nearly as elegant without them.

```golang
// RemoveIndex removes the item at the given index returning a new slice
// while preserving the references to each item in the original slice.
func RemoveIndex[T any](set []T, pos int) []T {
	if pos < 0 || pos >= len(set) {
		return set
	}
	return append(set[0:pos], set[pos+1:]...)
}
```

And here's an example test to go with it:

```golang
func ExampleRemoveIndex() {

	type SomeType struct {
		Thing string
	}

	one := &SomeType{`one`}
	two := &SomeType{`two`}
	three := &SomeType{`three`}

	set := []*SomeType{one, two, three}
	oneref := set[0]
	threeref := set[2]

	nset := filt.RemoveIndex(set, 1)

	fmt.Println(nset[0] == oneref)
	fmt.Println(nset[1] == threeref)

	// Output:
	// true
	// true
}
```

* go - How to delete an element from a Slice in Golang - Stack Overflow  
  <https://stackoverflow.com/questions/37334119/how-to-delete-an-element-from-a-slice-in-golang>
