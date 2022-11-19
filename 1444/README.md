# Use `x.` Instead of `command_` in bash Template

Yeah, after more than two weeks coding on stuff using `command_` instead
of the `x_` original command function identifier prefix in my bash
projects I'm shaking my head wondering what I was thinking. But while
going back to `x_` I decided to try `x.` since I have that for `CONFIG`
accessor functions already (`x.cast.dir.pending`). 

I checked the Internet and using dots is fully supported in bash (and
always has been). The only annoyance is clearly the bash Vim syntax
defaults to the same POSIX restrictions which don't allow it. Fuck that.
I just edited `/usr/share/vim/vim82/syntax/sh.vim` to add `.` anywhere
that it should have been allowed. This is a super annoying Vim bug, but
easily overcome.

So from now on `x.` in any code I write means that the function is
'exported'. 
