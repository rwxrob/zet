# Q: Are you going to write all the UNIX utilities in Go?

No. But many of them contain functionality that I have been using in my Bash scripts (in my dot files). For example, **select** from Bash is something I really need (so I made `choose`[^1]). I have been tempted to even writing things like `vim` in Go so that I can include them in my Bonzai stateful command tree monolith binaries that work on any computer anywhere (as opposed to having to install all that software) much like BusyBox has provided for Alpine Linux distro.

[^1]: https://github.com/rwxrob/choose
