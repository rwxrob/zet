# ZettelMark is Simplified, Semantic CommonMark

ZettelMark *is* CommonMark with the following additions and constraints.
These constraints are specifically designed to provide cognitive
boundaries resulting in content that is maximally succinct, digestible,
and composable as if applying the UNIX philosophy to knowledge:
communicate one thing well, and make sure it can be composed nicely with
others. This promotes compatibility with more limited text
representations (such as YouTube descriptions and Go documentation) as
well as simplify the requirements for any tooling to work with
ZettelMark. Relatively powerful parsers and utilities can be
created with simple bash scripts alone.

CommonMark is the most widely accepted standard for knowledge content,
but further redundancy reductions are required to keep things as simple
as possible:

* Only `*`,`**`,`***` for italic, bold, bold italic
* Only `1.` for ordered lists
* Only `* ` for unordered lists
* Just one space following list markers
* Lists must only be one level deep
* Everything at beginning of line (not within 3 spaces)
* Only `----` for horizontal rule / separator
* Use two or more trailing spaces for hard breaks
* Use three backticks for fenced content
* Use three tildes for fenced when contains three backticks
* Use four tildes for fenced when contains three tildes
* No space between opening fence token and keyword
* Use initial angle bracket for every line of quoted block

Note that CommonMark does not currently support tables. When and if it
does, they will not be allowed in ZettelMark because of how inaccessible
and difficult to parse they are. Use lists and formatting as an
alternative.

Additionally,  we need to add some semantics and constraints to the
overall format and organization of a ZettelMark document to make the
content easier to create, grok, and index:

* Only one heading allowed (level-1 title, first line)
* Title heading must be 52 columns or less (including prefix)
* Wrap *everything* but references block to 72 columns
* No images allowed whatsoever (100% accessible, only text)
* Substantial code, raw, and images should be in separate files
* Remember, code blocks will be automatically clipped
* No links anywhere but the final references list and video line
* Optional video link must be third line (own block)
* Video link must be less than 72 cols and start with 📺
* Optional reference links list must be last list block
* Optional tags line must be last line of file
* All reference links must be explicit and visible
* Block quotes must only contain paragraph and list blocks
