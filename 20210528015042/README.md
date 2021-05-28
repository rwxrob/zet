# Zsh is Dangerous for Floating Point Math

*Always use `bc` for floating point math of any kind in any shell
script.* Here's a great example of how Zsh fucks you while trying to
help you out. First, the script as you *should* write it using `bc`:

```sh
foo=2
bar=3.3
tot=0
tot=$(echo "scale=2; $foo + $bar" | bc)
echo $tot
```

This does exactly what you want with absolute control over the
precision.

```
$ sh /tmp/foo
5.3
```

In POSIX shell you could try to use floating point math and be reminded
that you just cannot. POSIX shell knows its limitations and openly
manages your expectation properly. This is nice and safe. You can't even
write it and have it run at all.

```sh
foo=2
bar=3.3
tot=0
tot=$((foo+bar))
echo $tot
```

This fails.

```
$ sh /tmp/foo
/tmp/foo: 6: Illegal number: 3.3
```

What about `bash`?

```
/tmp/foo: line 6: foo + 3.3: syntax error: invalid arithmetic operator (error token is ".3")
```

It also fails and tells you why, like a good friend, your second love
after POSIX. 

But then Zsh fucking lies to you. It pretends to know what you want and turns
out to fuck you over like your ex-wife.

```
$ zsh /tmp/foo
5.2999999999999998
```

If it had just failed like `sh` you would be better off, but instead it
happily accepted your shitty code that its floating point processor
can't handle you and now billions of people have died or gotten
instantly rich because of your dumb-ass use of Zsh instead of the
standard. But oh my God, Oh-My-Zsh is so fucking cool! 🤦

