# Use `command -v` Instead of `which` (Not POSIX)

Up until today I thought `which` was POSIX. It's not. Thanks to our good
friend Juan on the live stream who is dutifully using `shellcheck` to
look at everything we now know that `which` was never POSIX and that
`command -v` should be used instead. We tested all variations of `type`
and none of them with options are POSIX either even though I've always
used `type` to check for the existence of something since it looks for
aliases (and exported functions in Bash) but looks like `command -v`
from now on for everything.
