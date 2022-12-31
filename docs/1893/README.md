# Go maps are safe for concurrent reads (as best we can tell)

It would appear maps *are* safe for concurrent reads (but not writes). This is intuitive, but for a long time there's been confusion about how *theoretically* safe concurrent map *reads* are. 

Here's one quote that causes some of the confusion:

> Maps are not safe for concurrent use: it's not defined what happens when you read and write to them simultaneously. If you need to read from and write to a map from concurrently executing goroutines, the accesses must be mediated by some kind of synchronization mechanism.

But then, we read this on the official FAQ[^1]:

::: Quote

Q: Why are map operations not defined to be atomic?

After long discussion it was decided that the typical use of maps did not require safe access from multiple goroutines, and in those cases where it did, the map was probably part of some larger data structure or computation that was already synchronized. Therefore requiring that all map operations grab a mutex would slow down most programs and add safety to few. This was not an easy decision, however, since it means uncontrolled map access can crash the program.

The language does not preclude atomic map updates. When required, such as when hosting an untrusted program, the implementation could interlock map access.

Map access is unsafe only when updates are occurring. As long as all goroutines are only reading—looking up elements in the map, including iterating through it using a for range loop—and not changing the map by assigning to elements or doing deletions, it is safe for them to access the map concurrently without synchronization.

As an aid to correct map use, some implementations of the language contain a special check that automatically reports at run time when a map is modified unsafely by concurrent execution.

:::


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
* Race Condition in Golang - GeeksforGeeks  
  <https://www.geeksforgeeks.org/race-condition-in-golang/>
* Race conditions in Golang. Writing multi-threaded applications is...  
  <https://medium.com/trendyol-tech/race-conditions-in-golang-511314c0b85>

[^1]: Frequently Asked Questions (FAQ) - The Go Programming Language <https://go.dev/doc/faq#atomic_maps>
