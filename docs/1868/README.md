# Decided to go with "parser" over "scanner"

Because at the end of the day this is PEG we are working with and even though the parsing amounts to pointers to specific indexes in a `[]rune` slice it is still technically parsing it.
