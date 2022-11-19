# Shell `printf` is Not Same as Other Languages

If you are coming to shell programming (bash, POSIX, whatever) from
another language that has a `printf` function you likely will not expect
the way the shell version behaves. Most notably, it will repeated print
the filled in template string for each argument that follows it. Other
languages would give you some kind of error about the number or type or
arguments on syncing up.

This actually allows some pretty creative idioms. For example, you can
use this to join the incoming arguments to a function:

```bash
#!/usr/bin/bash

commands=(foo bar help usage)

join() {
  delim="$1"
  first="$2"
  shift 2
  printf "%s" "$first" "${@/#/$delim}"
}

join '|' commands
```
