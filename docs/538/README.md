# Uncommon Advantage of `if` Over `switch` in Go

Recently, I ran into a pretty substantial drawback of using `switch`
over more verbose `if` statements: `goto`. You cannot use labels and
`goto` for a specific `case` in a `switch` block. This is a deal-breaker
when writing performant code. So even though there is a ton of C code
out there (particularly scanners and parsers) that use `switch` for this
sort of thing, you simply cannot do it in Go. It's not that bad, really.
The most annoying part is matching several specific runes, but I've
learned that using `regex.MustCompile` at the package level for such
things is equally as terse and performant --- especially since a simple
regular expression like just a list of names like that --- compiles down
to effectively the same machine code as writing it all out longhand
like. So, "don't worry, write a regex" would seem appropriate in this
case.

    #golang #coding #tips
