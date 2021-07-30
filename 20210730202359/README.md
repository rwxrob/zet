# Use `watch` Instead of `-w` with Kubernetes

Just use `watch` and forget `-w` exists (unless you *really* need to
watch for only manifest changes). Here are the problems with `-w`:

1. Buggy and doesn't refresh well
1. Doesn't do what you *think* it should (only manifest changes)
1. Not included in other `kubectl` commands
1. Not consistent with UNIX philosophy
1. UNIX `watch` has been around forever
1. Requires one-line `exec` script (no aliases or functions)

Here's an example of `k` so that it will work with `watch`.

```sh
#!/bin/sh
exec kubectl "$@"
```
