# Use `exec bash -l` to Load `~/.bashrc` Changes

TLDR: Use `exec bash -l` to reload `~/bashrc` and `#!/usr/bin/bash -i`
when you want to use `complete -p <some>` in a script.

I've been forgetting something painfully obvious all these years and
finally been bitten in the ass for it. Don't forget the `-l` when using
`exec bash -l`. It turns out that this was really making all
my completion scripts unhappy because the `complete` builtin clearly
behaves radically differently when called from anything but a login
shell, as in, it does set *any* of the completion rules at all. This was
triggering the errors in all the completion scripts I've been sourcing
in my `~/.bashrc`.

If you want to see this run `complete -p kubectl` or something from the
command line.

```
$ complete -p kubectl
complete -o default -F __start_kubectl k
```

Then put it in a script and try to capture it's output.
You won't get what you think.

```bash
#!/usr/bin/bash
complete -p kubectl
```

Which produces:

```
$ /tmp/foo
/tmp/foo: line 2: complete: kubectl: no completion specification
```

In other words, you cannot call `complete` from a regular bash script. I
tried to hack to make it work by adding `-l` to your shebang line. But
that also fails. 

```
/tmp/foo: line 2: complete: kubectl: no completion specification
```

However, adding `-i` for interactive shell *does* work:

```bash
#!/usr/bin/bash -i
complete -p kubectl
```

And outputs what you would expect:

```
$ /tmp/foo
complete -o default -F __start_kubectl k
complete -o default -F __start_kubectl kubectl
```

