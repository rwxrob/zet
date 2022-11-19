# Bash Tab Completion Embedded in POSIX Script

I still cannot believe how easy it is to embed Bash tab completion into
the script that needs it. I really wish more people did it. It saves all
the hassle of extra installations into whatever `bash_completion.d`
directory and removes need for shitty `eval` calls in `.bashrc` files
(like Cobra and others require).

Here's an example that combines completion of command actions with
another list that simulates a bunch of possibilities. (I use something
like this in `sshkey` to complete either all the public key names or the
commands.)

```sh
#!/bin/sh

cmds="help usage"

help() {
  echo "would print help"
}

usage() {
  echo "usage: foo [COMMAND|name] [OPTIONS]"
}

list() {
  printf "one\ntwo\nthree"
}

default() {
  echo "default command"
}

# ---------------------- bash completion context ---------------------

# add `complete -S foo foo` to bashrc

if test -n "${COMP_LINE}"; then
  pre="${COMP_LINE##* }"
  for c in ${cmds:+${cmds} $(list)}; do
    test -z "${pre}" -o "${c}" != "${c#${pre}}" && echo "$c"
  done
  exit
fi

# ------------------------------- main -------------------------------

cmd="$1"
test $# -gt 0 && shift

case "$cmd" in
ls | list) list "$@" ;;
*) default "$@" ;;
esac
```
