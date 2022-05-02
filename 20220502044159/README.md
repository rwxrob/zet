# Scanning and Parsing Dilemma

I love coding parsers and scanners, but the two are very different. A
parser usually creates output in the form of an AST. A scanner just
validates and advances. The terms are very confusing and everyone uses
them differently. For example, a "parser" is also what people will call
something that parses the syntax of a file using a scanner that usually
uses an AST that was created originally from a parser. Then you can
throw the terms "lexer" into the mix.

Traditionally, the "lexing" is done in its own step to turn the bytes
into tokens, or "lexemes" (god why the crazy academic lingo). Then those
are compared to what is allowed by comparing them to what is allowed.

The dilemma is how to represent them both consistently in generated
code. There are three basic approaches:

1. Have both scanner and parser functions
1. Make everything take two argument, scanner and AST pointers
1. Create a parser that has a capture mechanism inside of it

In PEGN (unlike all the other PEG derivatives) I specify if a names rule
is going to capture anything at all. Of course, anyone can ignore those
things if they are just checking syntax. This means that the same tool
should be able to be unfettered from capturing an AST (or whatever) but
should be allowed to add it. I think this means that rather than having
a scanner and parser be two different things, that a single parser
struct should be created with an AST mode that can be set when capturing
the node tree is wanted.

    #coding #parsers
