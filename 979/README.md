# Personal Preference for Go Code Organization

I'm finding that the only place I need to write code these days is in Go
and in a particular repo format that combines the three major ways to
use that code, from a pragmatic perspective:

* A high-level package (functions and structs) (`pkg`)
* A Bonzai branch that calls into high-level package (`.`)
* A standalone executable wrapper for the Bonzai branch (`<name>`)

This is a timely realization as I start to produce a lot of libraries
that my Bonzai branches that require a strong amount of stability. For
example, my `rwxrob/json` module was created as a module. But, by not
putting it in `pkg` I've prevented myself from making a `json` Bonzai
branch out of it (without breaking things). The argument could be made
to leave the stuff intermingled I guess. But having everything in `pkg`
is a nice because the size of the statically linked binary containing
only those high-level functions is significantly smaller than if I
bundled it with all the Bonzai branch stuff.

I plan on fixing the `rwxrob/json` by simply leaving the stuff in both
places for now, at least until I can guarantee no dependencies on the
non-pkg stuff.
