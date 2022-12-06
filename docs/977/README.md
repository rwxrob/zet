# Simple command dependency checking in perl

Sometimes you just need to know if the commands are available. The `which` command is one way to do this without dependency on any shell.

```perl
for (qw( yq docker id )) {
    not `which $_` and say "Missing dependency: $_" and exit 1;
}
```
