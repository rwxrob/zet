# Use `echo "\$(<"$path")"` Instead of `cat` in Bash

It might be more to type, but it is hell-a faster and better on resources
to use the long-winded way of reading a file into a buffer variable and
then printing it out. The difference here, of course, is that it buffers
the whole thing instead out outputting each line as it goes, which
intuitively seems slower, but isn't.

```bash
#!/bin/bash
foo=/tmp/foo
echo "$(<"$foo")"
```

And, by the way, yes, you can have those double-quotes inside the other
double-quotes without a problem. Each subshell expansion has its own
quote context (something that took me *years* to realize).

    #bash #scripting #tips #linux #coding #100daysofcode #hacking
