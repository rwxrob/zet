# Execute Commands When File Changes with `entr`

Most people know about `entr` but I didn't know that to get multiple
lines of shell scripting to work you need `bash` (or some shell). This
is because `entr` makes a syscall to `exec` which requires a single
executable.

```
entr bash -c 'clear; go run main.go' <<< main.go
```

Or 

```sh
entr bash -c "clear; go test" < <(ls -1 **/*.go)
```
