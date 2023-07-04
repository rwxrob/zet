# Clean up shell artifacts on exit with trap

Apparently, this is the "idiomatic" way to clean up after yourself in shell/bash. The `trap` calls the command when the program exits. A `kill -9` would bypass the trap, however.

```sh
TMP_DIR="$(mktemp -d)"
# shellcheck disable=SC2064 # intentionally expands here
trap "rm -rf \"$TMP_DIR\"" EXIT INT TERM
```

Note that `trap` has "events" in addition to the normal signals.
