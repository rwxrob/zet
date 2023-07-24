# Stick with ksh-isms in your muscle memory, they work everywhere

* Being efficient and capable on *all* UNIX systems should be a priority.
* Bash is the default interactive shell on most all Linux systems.
* Zsh is default on macOS and Kali Linux.
* Ksh predates them both and contains commonalities that are better to memorize.

I was reading through the KornShell manual page and realized that most of the things that I love about bash originated in Korn. I also learned that bash (before version 4) couldn't even touch the functionality of Korn. For example, Korn shell has associative arrays and floating-point math *from the beginning*.

The importance of KornShell is therefore that incorporating usage of all its interactive functionality translates across the boundaries of all shells from which they are derived. So it is still a horrible idea to bake Zsh completion habits into your fingers. It is *always* better to bake `set -o vi` instead since that will work on any modern UNIX/Linux system all of which come with at least one shell that is KornShell compatible.

As for scripting, POSIX compliant BourneShell is still best provided it is safely paired with `shellcheck` and `shfmt`. Such scripts will work on any UNIX or Linux system created since 1985. Applications that have higher performance demands should use `dash` for its minimalism and speed. Anything that makes extensive use of subshells should probably be written in another language like Python, Perl, or Go.
