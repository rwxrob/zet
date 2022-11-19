# Usage, Synopsis, Help, or What?

Noticed recently that the `go` command does not dump the help text like
it used to do. That always annoyed me. I just wanted to know
specifically what about my arguments to it failed. Well, I'm having to
make an important decision about Bonzai related to this. I've covered
the ability for people to provide their own modular `help.Cmd` and make
it the first in `Commands` so that if no Call is provided it will
display as the default. But there is the lingering problem of providing
usage errors when something about a command isn't right but the entire
help might not be wanted. Traditionally, this is one line. But with the
combination of aliases and such the "usage" line for a monolith like my
`z` command can get pretty fucking long.

So I'm at a crossroads. I know for sure that all of that shit has to go
into clean sections of the `help.Cmd` output, but I cannot guarantee
that everyone will even use it. I could use inferred Usage strings (like
I have) and let developers override Usage (like I have) with something
that says, "usage: foo [COMMAND] (foo help for list of commands)". That
way they can make the note for anyone about where to go get more
information. I could also make a Cmd.Help first-class function field
that does special help things instead of making it a part of the
completion and Commands. Help and usage are different enough to warrant
a special field. It's like we want to have them there, and list them in
the overall help documentation, but we really don't want them ever
included in completions.

The thing about generic, hard-coded usage is that no one can change it
based on language. Everyone is stuck using the `usage` keyword.

