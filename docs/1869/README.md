# Packrat parsing

Packrat parsing[^1] is a uniquely modern approach to parser development based on the core assumption (from PEG) that everything to be parsed is loaded into memory and always addressable.

[^1]: Ford, Brian. "Packrat Parsing and Parsing Expression Grammars". <https://bford.info/packrat/>

> The core idea of the packrat parsing algorithm is incredibly simple. It boils down to: when you attempt to match a rule at a particular position, remember whether it succeeds, and if so, how much input it consumes. Because PEGs have no context-dependencies, if a pattern matches in a particular place in a string, it will always match there, exactly the same, regardless of where it fits into a larger structure. This means there’s a fixed number of combinations of grammar rules to match and string positions to match them at. There’s no need to try matching the same pattern in different ways at the same position. (Bruce Hill)[^1]

[^2]: Hill, Bruce. "Packrat Parsing from Scratch". <https://blog.bruce-hill.com/packrat-parsing-from-scratch>

The easiest way to write and maintain a packrat parser is using a functional approach by writing core parser functions with consistent signatures that return matches consisting of references to the underlying data and a limit set of meta functions for combining those parser functions.

