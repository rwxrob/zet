# Use colon operator in shell/bash to set defaults

The following are identical and work in *any* POSIX compliant shell (including ash, dash, ksh, sh, bash, zsh). This sets a variable to a value if variable was completely unassigned before (empty string *is* assigned).

WARNING: This will set to the value even if the current value is an empty string!

```sh
: "${TARGETDIR:="$HOME/.local"}"
true "${TARGETDIR:="$HOME/.local"}"
```

