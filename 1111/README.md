# Use `git grep -i` for Better `grep`

Git comes with its own `grep` that needs a `-i` to be case insensitive.
But beware, it only searches stuff that has been committed. I discovered
this when searching for a method I had just refactored into another file
and when to check that I got everything. The alternative `grep -r` would
have included all of `.git` as well (which can also be easily remedied
by wrapping `git` with your own version).
