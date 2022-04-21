# Bonzai Command Tree Go Module Structure

Decided that for monoliths, that are just composites of other Bonzai
branches that it is totally okay to have all that at the top. These
things are huge, they are composites of sometimes dozens, even hundreds
of other commands. So while the standard structure for a single Bonzai
branch is with `cmd` and `cmd.go` and high-level library stuff at the
root (no `main` package) the opposite is true of things like my `z`
command. *Everything* is at the top and everything is package `main`.
This also makes it easier for people to quickly grab and use your
monolith from anywhere.

```
go install github.com/rwxrob/z@latest
```

Why would I complicate that?

    #golang #bonzai #coding #tips
