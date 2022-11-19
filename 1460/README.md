# Use `RVAL` to Return Strings from Shell Functions

Even though the actual name `RVAL` is hard to remember and doesn't
matter. (I've see `RETURN` and `RSTRING` used as well.) This convention
gets around the fact that Shell script functions cannot return anything
but an integer. You could just as well `echo` the value. Many do. But
that does, in fact, force a subshell to do that work. I believe Bash has
been optimized to do it so quickly you don't even realize it. But
nevertheless, using `RVAL` is faster.

Note that this causes your shell scripts to *not* be asynchronous but
you should never use concurrency within your shell scripts anyway.
That's just fucking stupid.
