# Stop Using `tr` for Upper/Lower, Use `${foo,,}`

Seriously, if you are using Bash in 2021 or later you should be ashamed
of yourself for using `tr` subprocesses just to change the case of
something when they have been in Bash 4.0 parameter expansion since
the year 2009.

Here's a reminder:

```sh
foo=${foo,,} # all lower
foo=${foo,}  # initial lower
foo=${foo^^} # all upper
foo=${foo^}  # initial upper
```

Of course if you don't have that there's always the POSIX compliant
variety:

```sh
foo=$(echo "$foo" | tr "[:upper:]" "[:lower:]")
```
