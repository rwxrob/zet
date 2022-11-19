# Use `build` Shell Script Instead of `make`

People reach for `make` way to early. Pretty much every time a shell
script would have been a better option --- particularly because they are
far more powerful and efficient than `make`. One of the biggest
annoyances of using a `build` or `setup` is that you have to type `./`
in front for everything. This is easily remedied by the following one
line command that preserves your `PATH` security while turning `build`
into your `make` replacement. Name the following `build` and put it into
your general scripts directory somewhere. (You'll have another `./build`
in everything you are building.)

```sh
#!/bin/sh
exec ./build "$@"
```

If typing `build` gets annoying remember you have tab completion after
`bui` at least. Speaking of tab completion. If you have `bash` (and you
do have `bash`, right?) you can add automatic completion into your
`build` scripts by adding the following lines to the beginning of your
`./build` POSIX shell scripts. (I still write my build scripts in POSIX
shell even though I know I have `bash` because I want people with `zsh`
and others to still be able to use them (without bash completion, of
course):

```sh
cmds="sub go utils image push all"
if test -n "$COMP_LINE"; then
  pre="${COMP_LINE##* }"
  for c in ${cmds}; do
    test -z "${pre}" -o "${c}" != "${c#${pre}}" && echo "$c"
  done
  exit
fi
```

Put your commands on the top line. Now make sure you have the following in your `.bashrc` someplace:

```sh
complete -C build build
complete -C ./build ./build # in case you forget
```
