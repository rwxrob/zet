# Mandatory Monoliths, a List for Consideration

There are certain monolith tools that already enjoy the ubiquity of
being able to run anywhere:

* `go`
* `gh`
* `z`

I've been thinking long term about even the need for Linux at all for
more of these tools. Obviously, life will be better with it, but
theoretically I could build all the tools I use from Linux into my `z`
monolith. I won't know until I actually try it, also no idea how big it
is going to get, but I would bet it will still be hundreds of times
smaller than a single Electron app.

Here's a list of things for which I really want to see equivalents as
Bonzai branches:

* `vim`
* `lynx`
* `tmux`
* `git`

One of the important distinctions would be dropping `getopt` from
everything. These other tools really heavily depend on it. It might have
been a standard at one point, but it needs to fucking die if we are
going to move into the next age of terminal/command-line interfaces.

I guess I can take them one item at a time. After 2022 completes I'll
have written so many Bonzai branches that I'll really know for sure if
we can take it to the next level, one monolith to rule them all, shell
and commands integrated into a single binary.
