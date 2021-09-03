# When Shell Scripting Use `test` and `[[]]` Only

Ever feel uncomfortable with the way stuff inside double brackets in
bash is frequently *not* quoted? Regular expressions won't even work if
you do. That instinct is probably good, it means you are being careful
about POSIX's insecure shell injection vulnerabilities, but bash just
doesn't have them if you use double brackets. So it makes sense to use
`test` to flag POSIX and `[[]]` to identify bash conditions.

By eliminating the single bracket versions of conditional checks you
avoid problems and can enter the code in a way that is cleaner to read
and write. This also helps to immediately identify what type of code you
are dealing with.

The `test` and `[]` are exactly identical in every way in POSIX shell,
bash and all the others. This means they are extremely dangerous and
susceptible to shell expansion injection attacks (which is why all
variables should *always* be double-quoted --- especially in POSIX
shell).

It is not common knowledge that bash double bracket conditions `[[]]`
are immune to expansion injection attacks:

```
Word splitting and pathname expansion are not performed on the words
between the `[[` and `]]`; tilde  expansion,  parameter and  variable
expansion,  arithmetic expansion, command substitution, process
substitution, and quote removal are performed.
```

This makes double bracketed conditions automatically safer overall and
should be *always* preferred over single brackets when available.
Unfortunately, many shell scripts mix them for no rational reason. By
forcing the use of `test` you *know* you are using the unsafe version
and can intuit this easily because `test` is just another command after
all. Then, when you have bash, use the safer alternative. 
