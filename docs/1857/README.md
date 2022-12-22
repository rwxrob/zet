# PEGN scanner interface and functions

***Update:*** Dropping the `pegn.Scanner` interface approach in favor of providing tools to produce specialized scanners instead.

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
