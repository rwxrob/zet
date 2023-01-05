# Overview of functional scanning and parsing with PEGN

Recursive descent parsing with PEG and packrat is nothing new, but what if we encapsulated our PEGN rules scanners and parsers with metadata and specified an error stack in the scanner so that we get user-facing, human-friendly syntax documentation for free that travels with our scanner and parser methods (rather than just having a bare function do that).

Yes, (like the "PEGNs" we are, lol) we are heretically mixing syntax checking with our scanning and tokenizing, but Bryan Ford already started that revolution when he nailed the PEG paper to the doors of the church of Chomsky's context-free grammars. We are just "slaying that dragon." Ford first suggested PEG could blur the lines between such things that have been dogmatically observed by context-free grammars.

As to performance, newsflash: computers have memory now!

The AST required to do old-school syntax validation would then need to be walked to ensure the same level of multiple, recoverable scan error checking that we can do during the scan itself on the first pass. So either way, we take the hit. In this approach, however, there does not need to be an AST at all, nor a second phase of walking it for syntax validation.
