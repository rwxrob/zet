# CmdBox (Golang) or Perl for Prototyping?

When POSIX shell doesn't cut it I used to reach for Perl, then I started
reaching for Python, then I started reaching Bash (5+), and finally for
Go. It is remarkably easy and fast to code pretty much anything in Go.
I'm conflicted these days. My CmdBox utility commander library has made
throwing together a fully documented utility every bit as fast as doing
in it Perl. And my style of development --- first writing the docs ---
lends itself most to using CmdBox over anything Perl offers, even with
POD documentation. Obviously, projects like this that need that level of
document to be completed before continuing to keep sense of them are
immediately out of reach for POSIX. But Perl just prolongs the jump all
the way to a final tool. Yet Perl using `x_*` style tab completion with
reflection is not possible to do as quickly in Go, not at all.

So I've concluded that Perl is still way faster than both Go and Python
--- even Bash --- for rapid prototyping. I just need to remember to keep
the documentation to a minimum and actually to write it in `go doc`
format separate from the code. That way I'll be ready when I cut the
whole thing over to Go. And I also have to avoid the [problem with Perl]
at all costs.

[problem with Perl]: /20210530123523
