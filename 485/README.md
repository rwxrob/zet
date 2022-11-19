# Use `test -t 1` to Check for Terminal Output

`test -t` will check if the stream represented by the number is a
terminal (`tty`). By testing standard output you know that your code is
being piped to something else (not a terminal) if it is *not* true.

By the way, this is entirely different than figuring out if your code is
running in an "interactive" session with a user (which is usually not
really want to want, and it problematic to determine because it is at
least slightly different for every shell enough to make it inconsistent
to write compatible code).
