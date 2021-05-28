# Zsh is Dangerous for Floating Point Math

*Always use `bc` for floating point math of any kind in any shell
script.* Here's a great example of how Zsh fucks you while trying to
help you out. First, the script as you *should* write it using `bc`:

```sh
foo=2
bar=3.3
tot=0
tot=$(echo "scale=1; $foo + $bar" | bc)
echo $tot
```

Notice that Notice all the outputs are the same.

`$ sh /tmp/foo
/tmp/foo: 6: Illegal number: 3.3
rwxrob@live:zet(main)$ zsh /tmp/foo
5.2999999999999998
rwxrob@live:zet(main)$ vi /tmp/foo
rwxrob@live:zet(main)$ bc '1 +3'
File 1 +3 is unavailable.
rwxrob@live:zet(main)$ vi /tmp/foo
rwxrob@live:zet(main)$ sh /tmp/foo
.6
rwxrob@live:zet(main)$ vi /tmp/foo
rwxrob@live:zet(main)$ sh /tmp/foo
5.3

