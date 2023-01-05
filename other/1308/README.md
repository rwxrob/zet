# Workspace Container === Ultra-Light Linux Distro

I don't even know if the term *Workspace Container* is something I've
coined or what. I've never heard anyone else use this term. I do hope it
gets traction so we can at least explore the possibility.

I continue to get shit about how the size of my [`rwxrob/workspace`][ws]
container and I'm trying to find a way to elevator pitch why this makes
sense for a developer and researcher. So far the best way to explain it
is that workspace containers are actually just ultra-light weight,
terminal-only Linux distros.

Some really have a problem with this. But the fact is, it's a tool that
helps me do things that no virtual machine or cloud/network dependent
alternative can provide. Development teams have already realized this
value and created their own "developer containers" that have all their
tooling the way their team requires. This is just an extension of that
by making the thing something you actually work from (with all the
important persistent stuff mounted, obviously).

[ws]: <https://github.com/rwxrob/workspace>
