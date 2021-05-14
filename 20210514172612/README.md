# Use `id`, Not `$USER` and `$UID`

Recently I was reminded that `$USER` is often not defined, of that it
can be redefined any time. This is not only less secure than `id` it's a
pain in the ass because you never can rely on it being there. Just don't
use it, like ever. Here are the equivalent that are always there:

`$USER` -> `id -nu`
`$UID` -> `id -u`
`$GROUP` -> `id -ng`
`$GID` -> `id -g`

The `id` command is on *everything* including BusyBox containers. Go get
on one right now and see if it has `$USER`. I'll give you a hint: it
doesn't.
