# Under-Appreciated Speed of Bash

People love to bash on `bash`. After all it's "just" a scripting language.
But next time you are using it compare its startup and execution time to
Python for the same simple tasks. Because the `bash` interpreter is
already loaded into memory there is no need to load the entire
interpreter every time. In fact, while I don't have evidence for it yet,
I'm willing to think that even if you have another shell that the `bash`
interpreter loads into memory far faster than `python` or `perl` or
`ruby` (of course, `ruby`, which is slow as shit).

And another thing, because `bash` is so dense, and relies on the UNIX
philosophy to get things done, the parsing is wicked fast, far faster,
in fact, that `python` and `perl`. All that hard to grok chicken scratch
has value in that is far easier on the compiler than on our human eyes.

Here's the thing, I'm okay with it being more dense to read if it means
that is starts and runs as fast as it does. Sure it is bloated and
slower than `dash` (which is why Debian booted `bash` for startup
scripts a long time ago). But for the power bash brings to the table for
"just a scripting language" you have to give it credit. It fucking
rocks.

    #bash #rocks #scripting #linux
