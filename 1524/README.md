# Autodetection of KEG Node Isosec IDs

Since we are throwing out GitHub README.md as a method of browsing
(finally) we have the golden opportunity to create a recognizable,
parsable universal identifier for scoped usage within a single KEG site.
The Isosec is the standard, but could be confused with other numeric
data. So I'm thinking of simply adding a `K` in front of it (ex:
K20220427215109)

I kind of like that these are always going to show up in the spell
checker as being wrong. And I like that I can include one
(K20220427215225) wherever I damn well feel like it. This is *exactly*
what Luhmann did extensively throughout his paper system. I love that it
doesn't necessarily require the title of the zettel either, because the
title might change at any moment. This exact number of integers
following a `K` is virtually an impossible coincidence so we can even
use that for parsing zettels with a simple `scan.R` rune parser that
keys off of the capital `K`. This will make indexing "from" linkages
very easy to code.

I toyed with the idea of using an emoji, but that would violate "could
be done with just paper" cardinal rule.

    #keg #spec
