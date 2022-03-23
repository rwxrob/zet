# Use Go "Linker" `-ldflags` to Set Build Variables

I always have to look this up. Here's how to set variables using the
linker (technically not a Go thing). This doesn't work with constants
because it is using the linker to set the variables to their initial
values.

```go
package main

var Version string

func main() {
  fmt.Println(Version)
}
```

Then you have to use the `-ldflags` with it:

```
go build -ldflags "-X main.Version=v0.1.0" 
```

Don't forget the `main` in there. The linker needs it to find the right
symbol. Also, remember this only works for strings.

* See the `go tool link -h` for more about `-X`
* go - How to set package variable using -ldflags -X in Golang build  
  <https://stackoverflow.com/questions/47509272/how-to-set-package-variable-using-ldflags-x-in-golang-build>
