# Don't Let Print Fool You About 

By the way the `nil` prints out with `fmt.Print*` you would think that
the thing is there but just empty, when it fact it is not only empty, it
doesn't exist and will throw panics for `nil` pointer if you try to do
anything with them. Only *actual* pointers print `<nil>` when output.


```go
package main

import "fmt"

type blah struct {
	names  []string
	tags   map[string]string
	pnames *blah
}

func main() {
	b := blah{}
	fmt.Println(b.names)
	fmt.Println(b.names == nil)
	fmt.Println(b.tags)
	fmt.Println(b.tags == nil)
	fmt.Println(b.pnames)
	fmt.Println(b.pnames == nil)
}
```

Here's the output:

```
[]
true
map[]
true
<nil>
true
```
