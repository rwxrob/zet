# Go 1.16 `go get` Effectively Deprecated

Hit a nasty problem when trying to use the new way to install go stuff
from the Internet. Now that `go get` is pretty much dead (and `go
install` is the way to do everything) the caveat that `go install`
requires a specific `@<version>` is not immediately obvious, and even
when I figured that out and added `@latest` to all my `go install <mod>`
calls I was hit with the problem that any version before Go 1.16 has no
idea what to do with the stuff on the end. 

The solution is to just `sudo apt install golang-go` first to get a
version of Go on the system greater than 1.4. Then to use that to
"boostrap" install any version of Go beyond 1.16 (which as of this
writing is the current). I chose to clone the entire [GitHub repo]
directly into `/usr/local/go` (which is the place the standard install
instructions would have you extract the tar ball) and then build it with
`cd /usr/local/go/src; ./buildall.bash` to get the very latest. I figure
I need to see the source anyway. Often the source is faster than doing
research on the Internet to figure out what is going on. And looking at
the source is always good Go training in general. My solution is
captured in scripts in my [workspace container].

All the other solutions for getting the latest are quirky in some way.
The PPA approach is downright insecure (and `apt` even warns about
that).

[GitHub repo]: <https://github.com/golang/go>
[workspace container]: <https://github.com/rwxrob/workspace>
