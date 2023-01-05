# Use `apt-get` for Scripts, Not `apt`

Here's the part of the `man` page I missed:

> The apt(8) commandline is designed as an end-user tool and it may
> change behavior between versions. While it tries not to break backward
> compatibility this is not guaranteed either if a change seems
> beneficial for interactive use.

So it might not be that people don't now about the shorter version, if
it is in regard to a script there's actually a reason for it.

Keeping up with subtleties like this in a package manager is yet another
reason to centralize your mastery of a single, prominent package manager
system before branching out (and why learning `pacman` is such a fucking
horrible waste of time for most people wanting actual jobs using Linux).
