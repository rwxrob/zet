# Moving Installers to Bonzai (z) Tool

Perhaps the most annoying thing about working on multiple systems all
the time is that software never comes packaged well. It's either too old
in the official package repos (something the AUR tried to fix) or it is
a pain in the ass to install from source, or it is a release that has to
be pulled down, sometimes it is a Go project that can be installed with
just a `go install`. The point is, having a solid, universal way to
manage all the installs that you depend on is a critical thing to have
in your toolbox.

To that end, I've created some stuff in the `github` Bonzai branch and
will be adding more to it. One of the most common ways to get the latest
software is to download the latest GitHub release and place it into your
binary path (again, a pain point because everyone assumes a different
location when your ~/.local/bin is probably best). I don't really need
to do anything with releases since `gh` already does that, but perhaps I
could add them as well to avoid the `gh` dependency. The release file
names themselves almost always have the architecture and operating
system identifiers in the name and everyone has a different idea on what
that name should be. Some use `-` and others use `_`. But I'll just make
it into a Go template that can be added to the global config for a
specific GitHub repo.
