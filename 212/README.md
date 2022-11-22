# Idea of PEGN -> Compiled Regex Thwarted

Had an idea that I could take PEGN and create a regular expression string that would then be compiled. That way I could replace regular expressions for some things and return an AST inflated from the result. But any grammar that supports lookaround (which PEG requires) is simply unsafe to implement as a regular expression, if it is even allowed, which it is not in Go.

So what are the options?

Code generation, which, honestly, still fills like the best way to go because it is a tried and true way to do this. Sure you have to generate the code and cannot use PEGN for real-time grammar creation, but creating a web site that people plop PEGN into and get whatever code out on the other side is not a problem at all. Then they just add it to their library. This completely avoids any DDoS attack vulnerabilities and such that exist in regular expressions that allow lookaround (exponential possibility for abuse) versus Go regular expressions (just linear abuse possibility) and allows the generation of different types of parsers and scanners depending on the need instead of forcing everyone into the same design (which is what scan.X was doing, which
I've since abandoned, by the way).

* [20220406173710](/20220406173710/) Abandoning scan.X (from scan.R)
