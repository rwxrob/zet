# PEGN 2023 is amazing, I'm so pleased, soon no more regex for me

Here is the first sample of PEGN version 2023-04 used to capture the high-level blocks to be parsed from a KEG node:

```pegn
# KEGML spec.keg.pub/2023-04/kegml
# Copyright 2023 Robert S Muhlestein (rob@rwx.gg)
# SPDX-License-Identifier: Apache-2

# The Blocks rule specifies the major parts of a KEGML document as
# blocks without semantic consideration for how those blocks are further
# parsed. This parsing is generally done as the first pass. Each is then
# parsed individually as needed for additional granularity.

Blocks    <- TitleB (IncListB / Separator / BulListB / NumListB / FigureB /
             QuoteB / LatexB / FencedB / DivB / NoteB / ParaB)*

TitleB    <- '#' SP  Title EndB
Title     <- uprint{1,70}
IncListB  <- ('*' / '+' / '-') '[' .. EndB
BulListB  <- ('*' / '+' / '-') SP .. EndB
NumListB  <- digit{1,8} '.' SP .. EndB
FigureB   <- '![' .. EndB
QuoteB    <- '>' SP .. EndB
NoteB     <- '[^' SP .. EndB
LatexB    <- '$$' NL .. (NL '$$' EndB)
Separator <- '----'
FencedB   <- =FenceTok .. ($FenceTok EndB)
FenceTok  <- '~'{3,8} / BQ{3,8}
DivB      <- =DivTok .. ($DivTok EndB)
FenceTok  <- ':'{3,8}
ParaB     <- !SP .. EndB
EndB      <- !. / (NL / !. ) / NL{2}
.         <- rune

```

Note the `..` meaning "zero or more runes up to and including" (`rat/x.Toi`). There is also `...` (`rat/x.Tox`) which is non-inclusive. These make specifications so much cleaner than negative lookahead expressions (even though they are implied). I honestly don't know why someone else hasn't thought to put that rule into any of the hundreds of versions of PEG out there to date. All those negative lookaheads are very distracting from communicating the syntax or the grammar.

Note the `. <- rune` signifying the base unit. This automatically forces all the data to be viewed as that atomic unit. This allows PEGN grammars to set the base data to be used whether it by Unicode runes or bytes or ASCII characters or digits or even a Unicode class of characters from a specific language. This *incredibly* simplifies the grammar from the start. The `!.` from Bryan's original PEG paper is brought back as well, meaning "end of data". By default `.` is assigned `rune` when not specified.

Note that there are no longer any long arrows (`<--`). In fact, there are nothing but regular PEG arrows now. The entire association with a specific AST is now completely removed. Packrat parsers are encouraged to give names to every rule, no matter how insignificant. This motivates clearer grammar creation. For example, `Title` and `TitleB` above demonstrate that walking the results tree for `Title` would give the preferred output.

I've learned a lot more about the *right* way to approach data with PEG using "packrat" approach and pointers into that data enabling any possible collection of "parsed" spans that simply point to the beginning and ending (unlike traditional scanners). This has opened my eyes to the foolishness of forcing any hint of AST significance into any grammar captured in PEGN itself. It's been a painful reminder that parse trees and ASTs are two completely different things. Generating an AST from a parse tree is the better approach (than trying to define the AST in the specification itself) since it is far more flexible and allows shaking the tree of anything unwanted while keeping the original document. Besides, people want different parts of the parse tree at different times (Markdown blocks versus the spans that make them up, for example) so "significance" varies dramatically for each use of the grammar. So no more AST *in* PEGN.

Note the `=FenceTok` and `$FenceTok`. This is a new addition to PEGN syntax that indicates the specific match for `FenceTok` must be saved to memory and that specific matched version used at the `$FenceTok` location. This is far cleaner than all of the other tagging and capture options I have seen in other PEG extension grammars.

Note the following predefined tokens: `NL`, `SP`, `BQ`. This token set has been added directly to PEGN itself (no longer a separate import). All redundancies in the tokens have been removed in favor or a single, short alternative. These are not just literals and strings any longer. `NL`, for example, means `CR? LF`.

Note the `uprint` and `digit` from the original PEGN list of classes. These have remained and some have been corrected. But the biggest change is that all Unicode classes now get the `p{Basic_Emoji}` notation (borrowed from regular expressions). This means that the generation of all the classes and scripts from the Unicode spec is no longer needed. It also means that anything with a Unicode name can be referred to consistently and in agreement with how regular expressions denote such things. There is no `P{}` since this is covered by `!p{}` instead. All modern languages have full support for translating these Unicode class rules into "is" functions.

***And perhaps the biggest breakthrough of all:*** I've managed to create a one-to-one direct translation from PEGN to `rat/x` ("ratex") Go expression types. I've already been writing PEGN without the PEGN, meaning translating the PEGN "by hand" into the `rat/x` expression type that matches it. This means that generating fully-memoized packrat parser code in Go is beyond trivial now. This is mostly thanks to Go's *amazing* type switching and `any` type. Without it, it would not have been nearly as trivial or efficient. (Rust can't do *any* of this shit, btw. Pest is a fucking joke by comparison.) In fact, it is so easy that it can be done dynamically, at runtime, like compiling a regular expression only way faster, safer, simpler, and more powerful. PEGs can do things regex ever could or ever will be able to do. Regex is broken boomer tech at this point. PEGN is becoming so useful and fast that I'm quickly approach a critical point where I'll never use a regular expression in code again in my life.

Don't get mad, get busy.

I cannot wait to write my first LSP and other grammar-heavy applications with it.

Ugh, now I have to update the PEGN spec and `pegn.dev` site (which was #5 in a recent Web search for "PEG").

* <https://github.com/rwxrob/keg-go>
* <https://github.com/rwxrob/rat>
