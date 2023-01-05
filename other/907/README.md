# Are Functional Parsers Really That Much Slower?

The gold standard in Go Markdown parsers right now is GoldMark. The
source of GoldMark isn't that impressive, but it does have one thing in
common with Pandoc's Haskell parser: everything is a function.

When you want the fastest performance calling a function (that isn't
inlined by the compiler) slows stuff down. But when you want to write a
scanner or parser without using regular expressions that has near best
performance, a function version seems fine. It is certainly much, much
easier to code and maintain such a thing. It's also very easy to
generate the code for such automatically from things like like PEGN.

I don't know, but I feel like regular expression based parsers are just
as slow (if not slower) than those that just use functions. If for no
other reason than all the regex compilation that has to happen at
runtime. For example, let's say I could write a function to parse
exactly the same thing as a regular expression with capture parens. The
regular expression has to be compiled every time I do the match or at
least once for the entire program, which is also wasteful if you don't
need it. Writing that as a function means that it is compiled up front
into the binary at compile time, not runtime, and is available
immediately. Plus, simple functions have the possibility of being
inlined.

So I've convinced myself (again) that functional parsers are just fine
and dandy. Most people would not stress over these questions, but if I
need to optimize anything I can do it after the thing is done.

    #parsing #golang #performance
