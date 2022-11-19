# *None* of the Common Shells Have POSIX `local`

That's right `bash --posix` is *NOT FUCKING POSIX!* Then again, neither
is the default behavior or `ash`, `dash`, and the default setting for
`shellcheck` (which is such a shitty tool the more I use it made my
morons who have no fucking idea what POSIX *actually* means and are
leading a ton of beginners to their peril if they ever have to work
with an AIX system, or any of the millions of UNIX systems with *actual*
POSIX shell on them).

The issue is `local`, which we all know and love to make variables
behave as most humans expect within functions. But *local* is NOT
FUCKING POSIX! My God, this is where the whole `$REPLY` convention came
from in the first place. I hate it, but that is simply the reality.

This leaves me super conflicted. The chances of someone being burned by
`local` very low, but still.

This leaves me wondering what other non-POSIX lies are out there. For
example, I could swear that parameter expansion of any kind is not.
