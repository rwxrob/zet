# Shell or Go Language

These days everything for me is one or the other (when I have a choice).
Shell is *always* POSIX so that everything would even work on a BusyBox
container. And anything that needs more is in Go. The problem is picking
between them for most stuff that I do. I'm throwing together quick tools
all the time and they are *so* much easier in Shell --- especially with
tools like [curl], [jq], [yq], [find], [auth] (my own creation) and
simple `git grep`. Everything these days has a web API. That means all
you really need is shell and these tools.

For example, I started redoing my `twitch` script in Go and that sucked
in development on [cmdbox] and everything else. But the most annoying
thing about coding in Go (or any strict language) is all the noise (yes
even in Python). With a `curl` command you can see that *actual* stuff
being sent all in a single line. Other web client APIs spread that shit
out all over.

I think I'm realizing yet another situation where the [UNIX Philosophy]
has really somehow been lost. The reason I am *so* much faster with
shell scripting is because I use it every time I enter anything on the
command line, so the scripting of it is so completely and totally
intuitive and constantly fresh on my mind. It means that I can test
anything in the script quickly from the command line without any build
or test step at all.

[[POSIX Shell Works Everywhere]](/20210507150609)

[UNIX Philosophy]: <https://github.com/rwxrob/zet/search?q=UNIX%20Philosophy>
[curl]: <https://github.com/rwxrob/zet/search?q=curl>
[jq]: <https://github.com/rwxrob/zet/search?q=jq>
[yq]: <https://github.com/rwxrob/zet/search?q=yq>
[find]: <https://github.com/rwxrob/zet/search?q=find>
[auth]: <https://github.com/rwxrob/zet/search?q=auth>
[cmdbox]: <https://github.com/rwxrob/zet/search?q=cmdbox>

