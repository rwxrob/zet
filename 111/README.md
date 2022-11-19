# Use `test` Instead of `[ ]` in Shell Scripts

This year (2021) I've come to hate brackets in shell code. They are much
harder to type quickly, have very sensitive whitespace issues, and
frankly are just butt ugly --- especially when you have `set -e` on,
which gives you a beautiful and readable top-down shell script when done
right.

```sh
#!/bin/sh
set -e

test -d ~/repos
cd ~/repos
```

They also get around the entire globstar expansion issue because you
*know* that you are dealing with a shell command and not some sort of if
statement. You're just not. When I have `test` in front I remember that
everything is *still* just another shell command and to beware of
globstar.
