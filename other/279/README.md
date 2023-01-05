# Call Anonymous Function for Go `var` Assignment

Go has a specific order that code is evaluated:

1. Declarations with initial value assignment
1. Imported `init` functions
1. Package `init` functions
1. Everything in `main`

During the declaration and initial value assignment step you can call
functions that already exist (since compilation obviously happens before
all of this, something that isn't obvious to people used to languages
where stuff has to happen in order, like shell):

```go
package main

import "fmt"

var n = multiply(3, 5)

func multiply(x, y int) int {
	return x * y
}

func main() {
	fmt.Println(n)
}
```

But, you *cannot* assign to things that were previously declared in
package scope. You also cannot just call a function.

```
n = 14        // "expected declaration"
multiply(x,y) // "expected declaration
```

When you need to do this it is generally because you want to assign a
value or otherwise initialize the state of the package. That's what
`init()` is for.

But sometimes you don't need an independent function just to initialize
a single package variable. The solution is to call an anonymous function
during declaration and assignment:

```go
// Reg points to the the internal Register. Everything that imports cmdbox
// within a single executable shares the same Register.
var Reg = func() *register {
	r := new(register)
	r.Init()
	return r
}()
```

This has the added advantage of ensuring that the assignment runs
*before any init* is called allowing a sort of init before the `init()`
meaning that all the `init` calls can use the initialized value of your
package variable.
