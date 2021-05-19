# Why One-Line Scripts, Not Aliases or Functions

Aliases cannot be used at all from within `vim`. Even exportable Bash
functions required that I always use Bash for my interactive shell.
Scripts are also easier to share and include into containers as
independent POSIX shell. For anything more complex I'll compile a
[CmdBox](https://github.com/rwxrob/cmdbox) Go utility (like
[Pomo](https://github.com/rwxrob/cmdbox-pomo).

