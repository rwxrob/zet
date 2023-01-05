# Use `@` Magic with Bash Parameter Expansion

TIL that you can use all the wonderful parameter expansion stuff on
*each* item of an array if use the `@` sign in your parameter expansion
(and nothing else).

```bash
#!/usr/bin/bash

commands=(foo bar help usage)

join() {
  delim="$1"
  first="$2"
  shift 2
  printf "%s" "$first" "${@/#/$delim}"
}

join '|' ${commands[@]}
```

Which will print:

```
foo|bar|help|usage
```

