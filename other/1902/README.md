# Go projects in 2023: `bonzai` -> `rat` -> `keg` -> `pegn`

Outside of the REST API work I'm doing in Go (and the utility packages I'll be creating for that) the main development will be focused entirely on getting `keg` and `pegn` finished.

These have core dependencies on `bonzai` (which I focused heavily on in late
2021 and early 2022) and is ridiculously good and stable at this point
(deployed into production in several companies and the basis for at least one
EBPF-aware root kit).

As much as I love `keg` my favorite project in the last five years is turning out to be `rat`, the ultimate, scanner-less, PEG packrat parser in Go. I can compose complex grammars with nothing but Go structs. That's right, a meta-language for defining *any* grammar that is also compilable Go code. This makes code generation absolutely trivial and creation of ad-hoc grammars a no-brainer. These `rat/x` expressions are so much easier, faster, and safer than regular expressions is laughable that people still actually use regular expressions at all for grammar parsing. My `rat` is great, but there are a lot of others out there. PEGs are just so fucking superior to regular expression for *everything* --- but especially lookaround assertions. These are downright dangerous in regular expressions and generally forbidden by most because of it..
