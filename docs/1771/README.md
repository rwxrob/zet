# Removing item from a slice (array) in Go

Because Go uses arrays underneath a slice it is possible to keep the underlying array alive (on accident) while replacing (destroying) the slice that used it.

```golang

type SomeType struct {
  Thing string
}

one := &SomeType{`one`}
two := &SomeType{`two`}
three := &SomeType{`three`}

set := []*SomeType{one, two, three}

// create refs that will keep array alive after set dies

oneref := set[0]
threeref := set[2]

// overwrite set with new set slice

set = append(set[0:pos], set[pos+1:]...)

// these still refer to memory that was allocated for orig set array
// including the unused memory for item 'two' even though there is
// now no way to refer to it

fmt.Println(oneref,threeref)

```

* go - How to delete an element from a Slice in Golang - Stack Overflow  
  <https://stackoverflow.com/questions/37334119/how-to-delete-an-element-from-a-slice-in-golang>
* Reallocating underlying array of slice · golang-101-hacks  
  <https://nanxiao.gitbooks.io/golang-101-hacks/content/posts/reallocating-underlying-array-of-slice.html>
