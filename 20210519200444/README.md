# One-Line Shortcut Commands Beat Aliases/Functions

```
#!/bin/sh
exec go1.18beta2 "$@"
```

Aliases and functions are absolutely useless any time the `exec` system
call is involved, which is more common than you might think. Take, for
example, using the filter (`!`) command in vim. Sure functions will
work, but not aliases. Now consider `exec.Command()` in Go. You can
forget about your shell functions because Go has no way to resolve them,
and it shouldn't.

Shortcut scripts are also easier to share and include into containers as
independent POSIX shell, or to eventually replace with an actual binary
so that they work on *any* OS, not just UNIX/Linux.
