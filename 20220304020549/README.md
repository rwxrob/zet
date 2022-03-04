# Reminded How Valuable Bitwise Really Is

As a practical person with needs for things quickly rarely do I have a
need to do anything with bitwise, but that should probably change. It
really isn't *that* hard to use a bitfield for things instead of
blowing a whole variable, but let's be honest, that's not the mindset of
a bash coder. It is, however, of a Go coder, even one who's just making
things really quickly. Here are the basics for using them instead of
variables for flags.

The long and short of it is that use `|=` is to turn them on and `^=` is
off. All the other operators don't seem as useful to me for most things.
But they are worth mastering eventually as well. I always learn them and
then forget them because I use them so little day to day, but flags I
definitely will.

```go
package main

import "fmt"

const (
	asleep = 1 << iota
	dream
	nightmare
	walking
	_
	_
	_
	lucid
)

func main() {
	flags := 0
	flags = asleep | dream | lucid
	fmt.Printf("%010b\n", flags)
	flags ^= dream
	fmt.Printf("%010b\n", flags)
	flags |= dream
	fmt.Printf("%010b\n", flags)

	/*
		flags |= asleep
		fmt.Printf("%b\n", flags)
		flags &= asleep
		fmt.Printf("%b\n", flags)
		flags |= lucid
		fmt.Printf("%b\n", flags)
		flags >>= 3
		fmt.Printf("%b\n", flags)
		flags <<= 3
		fmt.Printf("%b\n", flags)
	*/
}
```

* Go Bitwise Operators  
  <https://www.w3schools.com/go/go_bitwise_operators.php>

    #golang #tips #bitwise #coding
