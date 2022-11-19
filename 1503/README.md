# Use `tcell` for Golang Terminal UI Applications

Looks like `tcell` is still far and away the best pure Go terminal
library. The main reason is its full support for terminfo and "all POSIX
systems".

> Tcell includes a full parser and expander for terminfo capability
> strings, so that it can avoid hard coding escape strings for
> formatting. It also favors portability, and includes support for all
> POSIX systems.
>
>The database is also flexible & extensible, and can modified by either
>running a program to build the entire database, or an entry for just a
>single terminal.

The `termbox` that I originally learned and used in several
projects is fine for most things, but `tcell` has first-class support
for pretty much anything anyone has done in a terminal in the last 30
years. It is very stable, still maintained (from what I can tell) and
continue to be the basis for `cview`, which I consider the best terminal
widgets library in Go, period (even though I have problems with where it
is hosted).

Looks like I'll be learning `tview` for now and `tcell` eventually.
Games in `tcell` would be a really fun project since you have direct
access to all the cells as if they were pixels in a graphic UI.

