# Using `test` in Bash Does Not Use Subprocess

At first I was concerned that using `test` instead of `[[]]` in Bash
would force a subprocess (as it does with POSIX shell). But thankfully,
it is reported as a builtin.

```
$ type test
test is a shell builtin
```
