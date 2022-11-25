# The Counter-Intuitive Problem with Code Generators

Code generators. They promise to save us time by writing all the code for us. But very often the reality is that later all that time savings is lost to time wasted working around the constraints of the generator. I've had a lot of personal experience with this very problem:

* SQL DDL generated from Dia UML
* OpenAPI generated Go code forced to use Gin
* PEGN generated Go code being sub-optimized and less performant
* YACC being abandoned by industry

In every case, taking bit longer to develop processes and practices for writing the code more efficiently *without generation* would have benefited the projects more in the long run. For example, writing a bunch of reusable PEGN scanners (with the option to capture the output transforming them into parsers when needed) makes short work when coding a functional recursive descent parser from scratch. Plus, you can rearrange them in different ways without being forced to write a new PEGN grammar and walk its AST.

There are a few specific cases where generators make obvious sense, like Rob Pike's automatic generation of the Go `unicode` package from the actual UNICODE specification CSV files (which I also do for generating the PEGN for UNICODE classes.
