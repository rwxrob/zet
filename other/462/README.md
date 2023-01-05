# Use Go Maps for Fastest Rune Class Lookups

I went looking through the fastest rune lookup tables in Go, the
`unicode` package, which is generated directly from the UNICODE
consortium CSV. I pondered the fastest way to check if any given rune is
in a set of runes. For a lot of stuff you could do numeric comparisons
for the value, but the best way to do it in a universal way is to create
a hash table, a go `map`. I had thought of getting fancy and putting
them all in a single `[]rune` slice, but then I have to search through
it, and at that point I'm just writing my own hash map look algorithm,
and linear searching ain't gonna cut it. So, the fastest is to just use
the highly optimized hash map that is already behind the `map` type. In
fact, this is why the `map` type is not locked in any way, because it's
so damn fast.

    #golang #coding #tips
