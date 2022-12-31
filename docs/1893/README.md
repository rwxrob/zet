# Go maps are safe for concurrent reads (as best we can tell)

It would appear maps safe for concurrent reads (but not writes). This is intuitive, but for a long time there's been confusion about how *theoretically* safe concurrent map *reads* are.

> Maps are not safe for concurrent use: it's not defined what happens when you read and write to them simultaneously. If you need to read from and write to a map from concurrently executing goroutines, the accesses must be mediated by some kind of synchronization mechanism.

However, it would appear from testing with `go test -race` and from the official FAQ (maintained by the Go team) that map reads are indeed safe for concurrency. This might explain why the `unicode` package has no additional safeties for concurrent reads of the read-only `RangeTables`.

The following code does *not* produce a race warning (although the same code, tweaked to write to `mymap` does):

```go
package foo

func MapFun() {

	mymap := map[int]int{0: 0, 1: 1, 2: 2, 3: 3}

	foo := func() {
		for {
			//fmt.Printf("foo: %v\n", mymap[2])
			_ = mymap[2]
		}
	}

	bar := func() {
		for {
			//			fmt.Printf("foo: %v\n", mymap[1])
			_ = mymap[1]
		}
	}

	go foo()
	go bar()

	<-make(chan int)

}
```

* <https://blog.golang.org/go-maps-in-action>

* Frequently Asked Questions (FAQ) - The Go Programming Language  
  <https://go.dev/doc/faq#atomic_maps>
* Race Condition in Golang - GeeksforGeeks  
  <https://www.geeksforgeeks.org/race-condition-in-golang/>
* Race conditions in Golang. Writing multi-threaded applications is...  
  <https://medium.com/trendyol-tech/race-conditions-in-golang-511314c0b85>
