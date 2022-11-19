# Smallest Possible Golang Web Server

This is handy for compiling a quick binary for working on network
plumbing with things like Kubernetes Ingress, Istio, Services, and
VirtualServices. Sometimes just having something quick and reliable
removes the different possible problems. That is why this doesn't even
attempt to read a file (which can get messed up by permissions,
container configuration, and other Dockerfile fails).

```go
package main

import (
	"fmt"
	"log"
	"net/http"
)

func main() {
	http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
		fmt.Fprintf(w, "Hey there.\n")
	})
	log.Fatal(http.ListenAndServe(":8080", nil))
}
```

This is also great fun for speed coding "katas" for ultimate beginners.
