# Don't Write Early Documentation *In* the Code

I've been burned more than once by prematurely writing inline
documentation in the code in languages that support it, such as Go
(golang) and Python. What happens is that you change something small and
it changes your API and all the docs become wrong or misplaced.

Some would argue this is why you should write the tests first, but that
is also naive. You cannot test something for which you are still
experimenting with the interface and how it will be used. Testing is
very premature at that point. That's the whole fucking point of rapid
prototyping.

A better approach is to create a `README.md` to contain it all and keep
it updated to help you think through what it is that you are build and
how it should eventually be tested. Then just keep changing it as you go
allowing for faster changes (more rapid prototyping) in the code. That
way you (and your team) have something solid to hold the project
together at the early stages without getting in the way. Ironically, C
developers have been doing this all this way since the beginning. You
will *never* find gobs of comments in C --- not only because it slows
the compiler down --- but also because it slows and complicates
development.
