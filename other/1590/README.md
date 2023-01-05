# Label, blocks, and `goto` in Go for Performance

One of the things you will immediately notice the Go standard library --- especially in the code (like the compiler and template engine that Pike himself wrote) --- is the highly performant use of labels, blocks, and the (infamous) `goto` statement. When I saw this I knew I was in love with Go and the designers way of thinking. Pike is the *perfect* person to design a highly performant, yet approachable enterprise language "to replace C" (as was his stated intention). His judicious (I would say "correct") use of `goto` separates him from the mob of `goto` haters who have no fucking idea why anyone should actually use it, and why in so many cases *not* using `goto` is the wrong design.

"Why?"

Because `goto` get's (nearly) inlined in the compiler as a long jump it is far more performant that forcing the loop to iterate again (and reset all the variable scopes and shit) and way more performant that calling out to a function. Functional compilers, or recursive-descent parsers that depend on functions are sure nice to read and follow, but they are fucking crazy slow in comparison (at least in any imperative language).

If all of that sounds like Klingon it's because no-one understands this when they first start to code. God, I feel like I still don't. But I've read and benchmarked enough of this stuff to realize *why* the standard `go` package has all of those `goto` statements and more. It's the reason I suggest strongly that people learn to code by reading good code, and that everyone eventually understand enough C to understand what their computer is doing at the lower level. You simply cannot understand that fully without understanding C, or even Assembly (for a given architecture).

So, how do you spot a noob trying to sound like a veteran? Listen to them spew hate for `goto` while they proclaim the advantages of Rust and Arch and Neovim. They aren't hard to find. Now you can spot them coming and avoid most things they have to say as being uninformed.
