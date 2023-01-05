# Call Shell Function Same as Script with `"$@"`

Remembering something simple like calling a shell function in the same
way that the shell script was called should be easy to remember, but
it's not. The answer is `"$@"` and *not* `"$*"`. 

> WARNING: *Do not forget the double quotes.*

The first is exactly identical, the second applies some extra magic to
make all the arguments passed to the script into one big long string,
which is not the same thing.
