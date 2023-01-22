# PEGN scanner interface and functions

***Sunday, January 22, 2023, 12:53:24PM EST***

The PEGN and ratex languages are now closely related (but not co-dependent). Every PEGN rule can be expressed as a ratex type directly. This means that "compiling" ratex is a matter of converting PEGN into ratex types and then passing those types to `rat.Pack`. There are some optimizations that I can do before passing though, like joining unnamed runes and strings.

----

***Update:*** No longer calling them `Parsers` because they aren't parsing anything. Using the words `Rule` and `Check` and `Results` now. Also distinguishing between AST and tree of results. Adding capture syntax to PEGN and dropping the `<--` operator. Every rule defined in an PEGN specification is significant. An AST should always be created from a results (parse) tree.

***Update:*** Dropping the `pegn.Scanner` interface approach in favor of providing tools to produce specialized scanners instead. Also calling them `Parsers` now that AST is included and referential rather than redundant copies of values.

----

📺 <https://youtu.be/zErrjCUEhG8>

My PEGN scanner implementation now conforms to a common `pegn.Scanner` interface so that other scanners can be implemented by people that conform to it. Why an interface?

* So that the library of scan functions can be interchangeable with
  different scanner implementations
* All this precipitated by BasicMD scanner/parser/AST
* Realized that my rwxrob/scan was actually *very* PEG specific
* Also realized fastest way to develop parser is to write PEGN and then
  scanner functions for recursive descent parser
* I'm souring on the idea of PEGN -> code generation (precludes
  optimizations that only a person could do)

Related:

* <https://github.com/rwxrob/pegn>
* <https://github.com/rwxrob/pegn-spec>
* <https://pegn.dev> (but a little older and out of date)
