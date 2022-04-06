# Abandoning scan.X (from scan.R)

After all that time I spent getting the scan.X interpreter to work
(which was very fun and educational) I've opted to stick with
hyper-optimized scanners and parsers written in the moment for a
specific purpose. It's not really that hard to write them and the
`scan.R` tool is still crazy helpful when doing it --- especially now
that I've added `scan.Trace` to it to watch it in action. (That's not even
the kind of thing you can do with regular expressions.) In short, just
fucking scan the runes and deal with it that way. Getting good writing a
scanner/parser quickly should be mandatory learning for anyone writing
applications with domain specific languages. I will still created a PEGN
code generator that I'll put up on the web as well so that people can
convert PEGN into whatever language they want. It's always good to work
out the syntax of a grammar in a meta first even if you code it by hand,
which is what PEGN originally was, just a way to represent a grammar.

For the record, I am using `regexp.MustCompile` much more again. I used
it extensively when writing my parsers for `skilbots` back in 2015.
Feels good coming back to it.
