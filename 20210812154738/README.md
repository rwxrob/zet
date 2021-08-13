# ZettelMark: Simplified, Semantic CommonMark+Tables

ZettelMark *is* CommonMark with the following additions and constraints.
These constraints are specifically designed to provide cognitive
boundaries resulting in content that is maximally succinct, digestible,
and composable as if applying the UNIX philosophy to knowledge:
communicate one thing well, and make sure it can be composed nicely with
others. This promotes compatibility with more limited text
representations (such as YouTube descriptions and Go documentation) as
well as simplify the requirements for any tooling to work with
ZettelMark. Relatively powerful parsers and utilities can be created
with simple bash scripts alone.

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
* Never HTML allowed in any way

CommonMark does not allow tables, but GitHub does. Therefore, GFM tables
are allowed in ZettelMark but with the following constraints to
facilitate parsing:

* Table block must begin with `|` (rest is fine to omit)
* If a block begins with `|` is *must* be a table.

|Name|Description|
-|-
Foo|The foo of it all
Bar|The bar as well

There are no plans to accept any other table format than what is
supported by GitHub and (if and when added) eventually CommonMark.
Sticking with this universal standards ensures the most sustainable
content syntax.

> ⚠️
> Tables are very hard for some people to process. Often putting the
> same information in a list, which could be read aloud without
> misunderstanding might be a better choice.

Additionally, some semantics and constraints to the overall format and
organization of a ZettelMark document are needed to make the content
easier to create, grok, and index:

* Only one heading allowed (level-1 title, first line)
* Title text must be 50 columns or less (same as Git)
* Wrap *everything* but references block to 72 columns
* Substantial code, raw, and images should be in separate files
* Remember, code blocks will be automatically clipped
* No links anywhere but the final references list and video line
* Optional video link must be third line (own block)
* Video link must be less than 72 cols and start with 📺
* Optional reference links list must be last list block
* Optional tags line must be last line of file
* All reference links must be explicit and visible
* Block quotes must only contain paragraph and list blocks
* Block quotes may begin with a semantic emoji line (`> ⚠️`)
