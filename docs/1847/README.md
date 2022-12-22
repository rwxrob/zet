# What is PEGN and why use it?

📺 <https://youtu.be/xuX0nbcJLYc>

Parsing Expression Grammar Notation (PEGN) is a language for defining languages. More precisely, it is a universal notation for expressing any grammar — including natural language — in a way that is easy to parse cognitively and programmatically without any specific application or implementation in mind. It builds on the best of existing meta and data structure languages such as PEG, ABNF, EBNF, and JSON.

***Motivation***

As technology increases in complexity and the need for better human-computer interaction becomes more pronounced, creating language grammars quickly and simply has become a critical need. PEGN is designed to meet this need. By allowing any data to be represented as a grammar and breaking it down into a universal form data can be combined, composed, and analyzed in remarkable ways.

Whether it be simply counting all the words in a document, creating a simple query language to make searching logs easier, coding a human-friendly interface to an otherwise complicated web API, simplifying the parsing of a form of a common Markup, implementing a full programming language that leverages the LLVM to quickly create a highly-performant compiler, or developing a binary language for moisture evaporators, PEGN addresses these needs by prioritizing the creation of other language grammars without weighing them down with any specific bias about how they should be implemented. In fact, PEGN is so flexible it can be used to define spoken and written natural languages and musical notation as well.

***PEG grammars are exploding, but inconsistent***

Since 2004 PEG grammars have exploded in popularity but the only thing that remains consistent is the wide variety of differences in their implementation and interpretation. Bryan Ford’s “example” PEG grammar is all but ignored as people continue to build their own syntaxes that have very little resemblance to the original and are more implementation code than PEG. This is demonstrated by many projects that contain both a grammar file for becoming acquainted with the syntax and another virtually identical file containing additional implementation specific code added to it so that a highly specialized code generator can use it. This redundancy and specialization are not only less sustainable but also highly rigid and counter-productive.

PEGN is a language grammar specification that does not allow implementation code so that the resulting grammar specifications stand on their own allowing the creation of any variety of linters and code generators in different language implementations, even different design variations in the same implementation language (AST, event callbacks, etc.)

***Original PEG lacks specificity***

For years ABNF and EBNF provide excruciating levels of specificity in their grammars but lack the obvious advantages of ordered priority and the simplicity of the original ASCII PEG grammar. For example, PEGN adds Count and MinMax to provide limits and adds Unicode tokens.

The hope is that the PEGN language itself can become a more explicit, better performing, and readable replacement for many grammar meta-languages and inline regular expressions. Code generators producing parsers of different types and in different implementation languages can
be created from the same grammar specification expressed in PEGN. PEGN parsers and standard libraries can even provide highly optimized handling of PEGN grammars included directly in code as strings and constants much like compiled regular expressions are handled today but with much greater clarity and efficiency.

* blah https://github.com/rwxrob/pegn-spec
* blah https://github.com/rwxrob/pegn
* blah https://pegn.dev

