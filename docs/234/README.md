# KEG Mark Parser Showing Promise for Code Gen

I'm coding the KEG Mark (KEGML) parser from scratch using established
best practices for creating a functional, infinite-look-around parser
and I'm using a PEGN document to organize the logic (as usual). But I'm
not using any of the existing PEGN code generators mostly because my new
`scan.R` is a lot more efficient and each to deal with.

One of the things I've noticed is that the patterns of code in each of
the parse methods are very simple and repeatable. This is very
encouraging because it means being able to easily generate it later with
`keg mark gen foo.pegn` (or something like it). That's a bit deal to me.
I have a lot of plans for different grammars and variations on existing
grammars and regular expressions just don't cut it. They are slow,
complicated, and cause a lot of code obfuscation (yeah, I never liked
Lex/Yacc because of it, and neither to people like Rob Pike). A simple
(albeit long and wordy) parse function will always be faster and easier
to debug than anything involving regular expressions that must be
compiled before they can be used.

I'm also realizing that we can generate everything in a single
`parser.go` file including the option to embed a copy of the `scan.R`
directly in the file. The hardest part is working in custom error
messages. But I think we can create plenty of generic errors to cover
the different situations and just allow them to be overridden.

    #golang #pegn #coding #gen #keg
