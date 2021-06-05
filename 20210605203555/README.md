# Bash Completion Reserves `quote` and `dequote`

Bash completion `/usr/share/bash-completion/bash_completion` reserves
`quote`, `dequote`, and `quote_readline`. I discovered this while
working on my `quote` CmdBox command module (which produces a `quote`
binary that was being ignored). For an intents and purposes this is a
bug because it effectively adds a very key reserved keyword for
Bash shell completion to work (`_parse_help` and `_parse_usage`) without
any documentation at all. Unsetting or overriding it will break
completion. That's a fucking bug.

To get around it (rather than fight with the Bash team about the nature
of this bug) I just changed my command to `quot`, and let's face it, no
one wants to type that final `e` anyway. ;)

