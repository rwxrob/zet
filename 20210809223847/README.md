# Q: What is a UNIX/Linux "filter" command?

A *filter* (in UNIX/Linux parlance) is a command that accepts standard
input with the intent to transform or "filter" the incoming lines or
buffer. Modular, composable, filters are the UNIX way, not plugins.
Learning to use filters in pipelines and from within Ed/Vi/m are
critical UNIX/Linux scripting skills and require a good understanding of
the UNIX philosophy.

Filters are superior to other plugin approaches because they so easily
attach together into pipelines.


```sh 
#!/bin/sh

while IFS= read -r line; do
  echo "${1-#}" $line
done
```

```bash

myfunc() {
	_filter "$@" && return $?
  echo "${1-#}" "$*"
}

_filter(){
  [[ -n "$1" ]] && return 1
  while IFS= read -ra args; do
    "${FUNCNAME[1]}" "${args[@]}"
  done
}

_buffer() {
  [[ -n "$1" ]] && return 1
  "${FUNCNAME[1]}" "$(</dev/stdin)"
}
```
