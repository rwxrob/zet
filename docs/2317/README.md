# Adding automatic bash completion for functions in build

I've always hated Makefile abuse. I call them "PHONY" Makefiles because they don't even use the original intent of make at all. One reason people use make is because of the built-in rule completion. But with just a `complete -C build build` they would have automatic completion using the exact same file. (This is yet another reason that bash is far superior to all other shells.)

```bash

x.foo () {
  echo foo
}

# --------------------- completion and delegation --------------------
#      `complete -C foo foo` > `source <(foo bloated_completion)`

while IFS= read -r line; do
  [[ $line =~ ^declare\ -f\ x\. ]] || continue
  COMMANDS+=( "${line##declare -f x.}" )
done < <(declare -F)
mapfile -t COMMANDS < \
  <(LC_COLLATE=C sort < <(printf "%s\n" "${COMMANDS[@]}"))

if [[ -n $COMP_LINE ]]; then
  line=${COMP_LINE#* }
  for c in "${COMMANDS[@]}"; do
    [[ ${c:0:${#line}} == "${line,,}" ]] && echo "$c"
  done
  exit
fi

for c in "${COMMANDS[@]}"; do
  if [[ $c == "$EXE" ]]; then
    "x.$EXE" "$@"
    exit $?
  fi
done

if [[ -n "$1" ]]; then
  declare CMD="$1"; shift
  for c in "${COMMANDS[@]}"; do
    declare cmd=$(command -v "x.$c")
    if [[ $c == "$CMD" && -n "$cmd" ]]; then
      "x.$CMD" "$@"
      exit $?
    fi
  done
fi
```
