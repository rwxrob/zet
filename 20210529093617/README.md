# Perl `pae` Better Than `sed` and/or `awk`

You can remember it because it sounds like `pay` but it is actually
`perl -paE` and it is the most powerful line filter you have in your
utilities tool box. Here's one line shell script that will enable you to
even use it from within Vi/m. 

```sh
#!/bin/sh
exec perl -paE "$@" # so fucking better than sed and/or awk
```

Sometimes you don't have `perl` and are forced to use `sed`. If that is
the case you have much more difficult problems because `sed` BRE regular
expressions are widely known to suck ass. They are one of the major
reasons that `perl` was invented by Larry in the first place. But you
probably won't appreciate that until you have tried it and understand
both of the regular expression syntaxes (and learning just one is a
bitch). Perl regular expressions (PCRE) have been the industry standard
for more than two decades.
