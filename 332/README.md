# Use Go `if err != nil` Idiom

📺 <https://youtu.be/b1e7usVMCe8>

```go
package main

import (
	"fmt"
	"log"
)

func blah() string {
	return ""
}

func bar() (string, error) {
	return "bar", nil
}

func main() {
	val, err := bar()
	if err != nil {
		log.Println(err)
    return
	}
	fmt.Println(val)
}
```

Using this idiom is common, correct, and clean. People complain, but it
forces dealing with the error early. (Exceptions will never be a thing in
Go. They've been proposed twice and shot down for good reason.) It is
also idiomatic to return at least two value from most functions, the
value, and an error. Get into the habit of doing this.

    #golang #nil #tips #errors
