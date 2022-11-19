# Use `vim -R` and `vi -R` Instead of `view`

I have used `view` all my life. At work when I'm on a system reading
through highly critical configuration files to which I have full write
access it is just too fucking dangerous to open it in `vi` with the
default write mode. This is the sort of stuff that should make any
experienced operations person very nervous. This is why `view` was
created.

I'm now learning, however, that there are at least two good reasons to
use `-R` instead, which is the functional equivalent of `view` and works
on *everything*.

1. On systems that have `vi` installed in addition to `vim` you get the
   old `vi` (even if `vim` is installed) without all the great `vim`
   navigation and syntax highlighting you have come to love.

1. NeoVim (`nvim`) does not install a `view` at all. In fact, they
   ripped it out as is documented in the project change logs. While I
   think this was a fucking stupid decision and you should only consider
   the NeoVim alpha software only after putting `vi` and `vim` into your
   muscle memory and `.vimrc` so you aren't fucked when you don't have
   it, well, you still just might want an alternative to `view` even if
   you only develop on stuff locally.
