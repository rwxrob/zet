# Need Two Utility Rune Scanners

Realizing that my `scan.R` is trying to do too much. The cursor
positioning is amazing when you really need a human friendly view of
things, but the rune and byte counts restrict it to only iterating one
rune at a time to keep them all up to date. This is tremendously
inefficient for high-performance scans where a precompiled regular
expression could jump to a position far into the remaining buffer and
just update the scanner to that position. Making a jump like that breaks
my current `scan.R` because I lose all the data that would have been
accrued in the cursor while scanning all of those, some would say
wastefully.

I'm also falling out of love with my `scan.X` notation based on how much
it obfuscates what the scanner is actually doing. The `z.P` parsing
struct didn't cut it. I can get it to work, but wondering if I really
want to. The downside of not doing `scan.X` is that it will be harder to
directly translate from PEGN. But another idea occurred to me, I could
write a PEGN to regular expression generator that might actually end up
being faster than everything else I've been working on. Since there is
such strong support for regular expressions everywhere (specifically for
PERL) there would likely be wider adoption of such a generator.
Moreover, I could create a `pegn.MustCompile` that creates a number of
regular expressions that it encapsulates into a struct and could then
use for Match and Parse stuff.

Bottom line: I need a fucking fast `scan.R` and another one that wraps
`scan.R` somehow to provide the human-friendly cursors, which, honestly,
are not really that needed in my world. Mostly, I just want to write one
off scanners *very* quickly and leverage regular expressions where it
makes sense. This is how people have been creating parsers since the
beginning and I'm starting to see the logic of many of their decisions
better. Regular expressions (which I love) are not enough by themselves.
But when judiciously used to identify tokens they make scanning and
parsing very easy to grok and highly performant. This is why lexx/yacc
have been using them for years.

    #golang #coding #tips
