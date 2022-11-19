# Simple Command Dependency Checking in Perl

```perl
for (qw( yq docker id )) {
    not `which $_` and say "Missing dependency: $_" and exit 1;
}
```
