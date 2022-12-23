# Using slices as arguments to functional scanners in Go

Strings *always* point to immutable memory segments. Slices always point to specific locations of an underlying `array` memory segment. So, the most important thing to remember when creating PEG parsers is to load all the `[]byte` slice into a `string` and then convert to a `[]rune` slice since casting a slice (`byte` or `rune`) to a `string` will force the creation of a new sequence of underlying bytes in memory that are not immutably associated with that string. So, in order to keep scanner functions from using unnecessary memory it is imperative to use slices of slices only, and to pass them to the scanner functions. In fact, it is likely more memory efficient to cast a string literal to an array of runes for comparison, than to cast a slice from the main buffer to a `string` (which creates a new, temporary `string` at runtime)

> In Go, a string is in effect a read-only slice of bytes.

> Slicing does not copy the slice’s data. It creates a new slice value that points to the original array. This makes slice operations as efficient as manipulating array indices. Therefore, modifying the elements (not the slice itself) of a re-slice modifies the elements of the original slice.


* go - Understanding Golang memory management with large slice of strings - Stack Overflow  
  <https://stackoverflow.com/questions/52229040/understanding-golang-memory-management-with-large-slice-of-strings>
* Go Slices: usage and internals - The Go Programming Language  
  <https://go.dev/blog/slices-intro>
* Does Golang do any conversion when casting a byte slice to a string? - Stack Overflow  
  <https://stackoverflow.com/questions/20985536/does-golang-do-any-conversion-when-casting-a-byte-slice-to-a-string>
* Strings, bytes, runes and characters in Go - The Go Programming Language  
  <https://go.dev/blog/strings>
