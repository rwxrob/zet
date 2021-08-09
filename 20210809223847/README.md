# Q: What is a UNIX/Linux "filter" command?

Any command that accepts standard input with the intent to transform or
"filter" the incoming lines or buffer. Learning to use filters properly is a critical part of mastering UNIX/Linux and the UNIX philosophy specifically.

Filters are superior to other plugin approaches because they so easily attach together into pipelines.


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

_filterbuf() {
  [[ -n "$1" ]] && return 1
  "${FUNCNAME[1]}" "$(</dev/stdin)"
}
```
