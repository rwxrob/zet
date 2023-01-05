# Focus on scanner/parser functions over AST generation

While creating the `keg` command branch I realized that `keg node parse tags` would be forced to parse the entire document just to get to the AST so I could then walk it and find the tags. Yeah, it was one of those "how could I have been so blind" moments.

By focusing on writing scanner functions that *have the option to write output* --- instead of always obsessing about AST driven parsing --- one gains the advantage of being able to rearrange those functions depending on the application without rewriting a PEGN sub-grammar just to capture it.

Keeping with my example, if I only want the tags, which are contained in the very last block of the KEGML file, all I really need to do is parse all the high-level blocks first and then skip all those blocks to get to the last one. There's no need to parse the other blocks into spans and such because there is no *actual* need for them at all. By focusing on functions I simply write only the code necessary to get to what I want. I'm not forced to parse the whole thing.

So the secret is in the library of scanner/parser functions and a simple, performant rune scanner with tracing and such to facilitate rapid development of task-specific recursive descent parsers.
