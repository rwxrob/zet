# Use curly brackets in POSIX shell to group lines of code

I feel stupid that I didn't know this before. But the `goreleaser` code (which is absolutely beautiful) has this block in it that allows the `test` command to be combined with multiple lines of shell code. I've tried (and failed) to do the same with parenthesis before but this actually works. I do also love this person's use of `test` instead of `[]` which is often misused. `test` explicitly reminds the coder that command line expansions are still happening (because it's a command) unlike bash double brackets (`[[]]`) which do *no* expansion whatsoever.

```sh
test -z "$VERSION" && {
  echo "Unable to get goreleaser version." >&2
  exit 1
}
```

Of course, this can also be written as a plain if statement (which is usually how I have been doing it).


```sh
if test -z "$VERSION"; then
  echo "Unable to get goreleaser version." >&2
  exit 1
fi
```
