# TIL `paste` Command Exists and OMG

I'm really wondering when I will stop discovering wicked amazing shit on
the command line that I never learned about until now. The `paste`
command is the latest. If you are doing things using the UNIX (filter)
way then you will immediately understand the value of joining the lines
of one or more files such that line one of every file is now on line one
of the output separated by a delimiter of your choice (tab by default).
This has so many possibilities it's just mind-boggling to me.

I discovered it looking for a simple way to dump bash 4+ associative
arrays (which are relatively new to me) and found this amazing gem on
Stack Exchange (I guess I'll have to stop hating on SE a little now):

```bash
declare -A foo=([a]='an a' [b]='a bee')
paste -d= <(printf "%s\n" "${!foo[@]}") <(printf "%s\n" "${foo[@]}")
```

```
b=a bee
a=an a
```

This works because of the rather unintuitive (but awesome) way `printf`
handles more arguments than it has fields for, it repeats automatically.
In this case it is used to produce what is essentially a file with all
the keys, then another with all the values, then `paste` them together
with an equal sign delimiter.

It is worth noting that this mind-blowing hack is *only* possible
with bash, not Z-fucking-shell, and certainly not POSIX or ksh. If you truly understand that little hack, you are a long way toward
understanding the most powerful aspects of bash (and the reason I
really do not miss Perl that much).

    #bash #shell #scripting #paste #unix
