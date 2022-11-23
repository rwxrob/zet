# Command `pager` isn't just `less` or `more`

So I was creating a pager Go Bonzai branch package[^1] and named the binary `pager` and ran into something really odd. Suddenly, `git diff` was running my `pager` program and not diffing any more. At first I thought `git` had some pager magic going on (which it does) but it turns out that there is a `/usr/bin/pager` that actually exists. I can't say how long its been in Linux, or if it is also a UNIX thing. But it seems pretty standard.

The `man man` page has this to say:

    -P pager, --pager=pager
       Specify which output pager to use.  By default, man uses pager, falling
       back to cat if pager is not found or is not executable. This option
       overrides  the  $MANPAGER environment  variable, which in turn overrides
       the $PAGER environment variable.  It is not used in conjunction with -f
       or -k.

       The value may be a simple command name or a command with  arguments, and
       may  use shell quoting (backslashes, single quotes, or double quotes).
       It may not use pipes to connect multiple commands; if you need that, use
       a  wrapper  script,  which  may take the file to display either as an
       argument or on standard input.

So it looks like this has been a part of UNIX from the beginning. The binary `pager` has always been used, even if `$PAGER` isn't defined. This means naming *anything* `pager` is a big no-no unless you really are committed to taking over paging of *everything on the system* with your fancy, custom version[^2] (which I'm not).

[^1]: https://github.com/rwxrob/pager
[^2]: http://www.jedsoft.org/most/

```cli
$ type pager
pager is hashed (/home/rwxrob/.local/bin/pager)
$ which pager
/usr/bin/pager
$ exec bash -l
$ which pager
/usr/bin/pager
$ type pager
pager is /usr/bin/pager
$ pager -l
There is no -l option ("less --help" for help)
Missing filename ("less --help" for help)
$ ^Cger -l
$ ls -l `which pager`
lrwxrwxrwx 1 root root 23 Apr 20  2022 /usr/bin/pager -> /etc/alternatives/pager
$ ls -l /etc/alternatives/pager
lrwxrwxrwx 1 root root 13 Apr 20  2022 /etc/alternatives/pager -> /usr/bin/less
$ ls -l /usr/bin/less
-rwxr-xr-x 1 root root 195K Mar 24  2022 /usr/bin/less
$ man pager
```
