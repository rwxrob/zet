# Bash is the Safest Shell Scripting Language

Bash has had its security problems in the past (ShellShock comes to
mind) but all things considered it is the safest UNIX/Linux shell
scripting language on the planet when you consider how it handles double
brackets and reliably handles floating point math consistently (it
doesn't at all forcing you do it right with `bc` instead of trolling you
like `zsh`). Beginners cannot subject themselves to troubles with 

The following proves that there is no shell expansion done at all within
the double brackets:

```bash
#!/usr/bin/bash

if [[ -r some* ]];then
  echo yep
fi
```

Notice how I have to actually create a file with a start (\*) in the
name for this to work:

```
$ touch something
$ ./foo
$ touch some
$ ./foo
$ touch 'some*'
$ ./foo
yep
```

