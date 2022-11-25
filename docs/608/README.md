# Better Bash `PATH` Management with `pathprepend`

Almost no one actually has their `PATH` right in their `.bashrc`. It is
usually just blindly appended, which makes simple shell
(re)initialization with `exec bash` impossible. Sometimes people blow
out what was already there from the system (which I have done many
times). 

A better approach is to prepend and append to the existing path
and remove any previous duplicate before doing so. This has the added
advantage of allowing you --- on the fly --- to change your path easily
during any terminal session without fucking with with your `PATH` at
all.

One caveat, remember that the *last* argument to `pathprepend` will
appear first in the path.

```bash
pathappend() {
  for ARG in "$@"; do
    test -d "${ARG}" || continue
    PATH=${PATH//:${ARG}:/:}
    PATH=${PATH/#${ARG}:/}
    PATH=${PATH/%:${ARG}/}
    export PATH="${PATH:+"${PATH}:"}${ARG}"
  done
}

pathprepend() {
  for ARG in "$@"; do
    test -d "${ARG}" || continue
    PATH=${PATH//:${ARG}:/:}
    PATH=${PATH/#${ARG}:/}
    PATH=${PATH/%:${ARG}/}
    export PATH="${ARG}${PATH:+":${PATH}"}"
  done
}
```

You can also add this simple one-line `bash` script to your utilities to
allow your path to be pretty printed anywhere on the terminal, including
from within a Vi/m session (which aliases cannot do).

```bash
#!/bin/bash
echo -e ${PATH//:/\\n}
```
