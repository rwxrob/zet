# Function declarations without bodies in Golang

What the hell is going on here? This is the implementation of the `os.CreateTemp` to get a random number for the name.

```go
// fastrand provided by runtime.
// We generate random temporary file names so that there's a good
// chance the file doesn't exist yet - keeps the number of tries in
// TempFile to a minimum.
func fastrand() uint32
```

There is no function body. I've never seen that before. Well (thanks to ChatGPT) it turns out this is just a function declaration like in C for a function that is implemented elsewhere, in this case the runtime itself (coded in C). By why require the declaration at all? This is all of what ChatGPT has to say about it.

## ChatGPT response

In Go, a function without a function body is known as a "function declaration" or a "function signature". These declarations are used when you are defining an external function that is implemented in another package.

The function declaration specifies the function's name, input parameter types, and return types, but it doesn't include the code for the implementation. Here's an example:

```go
package mypackage

// Function declaration or signature
func SomeFunction(x int) string
```

In this example, the `SomeFunction` function is declared with an `int` input parameter and a `string` return type. The actual implementation of this function will be present in another package.

By using function declarations, you can define the interface for a set of related functions without implementing them directly in your code. This is particularly useful when you want to define abstract interfaces or work with external libraries that provide function implementations.
