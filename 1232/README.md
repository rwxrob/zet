# Optionally, Start with a Linux Workspace Container

Before you have learned enough to customize your own environment you
might want to borrow someone else's, mine for example. I've created a
[personal workspace] that has *exactly* the same system with all its
configurations that I use every day. In fact, I actually use it to do my
day job. All beginners have to do is the following to get up and running
with it immediately:

[personal workspace]: <https://hub.docker.com/r/rwxrob/workspace>

```sh
docker run -it --rm rwxrob/workspace
```

For something more persistent (the files you create get saved) I've
create [a script] that you can download and use instead to setup a
workspace that keeps all your files in a `Workspaces` directory folder.
But there's a chicken-and-the-egg problem because you have to have a
terminal and minimally know how to use it before you can do these
installation steps.

[a script]: <https://raw.githubusercontent.com/rwxrob/dot/main/scripts/ws>

Once downloaded you need to put it somewhere and make it runnable.
Perhaps something like this:

```sh
mkdir -p ~/.local/bin
mv ~/Downloads/ws ~/.local/bin
chmod +x ~/.local/bin
```

> ⚠️  You should always have someone you trust check the file out and
> make sure it doesn't have anything bad in it. Normally, you would also
> do a checksum validation to do that, but just look it over. You should
> *never* download and run something from the Internet without first
> checking it out --- even if you trust the source or person hosting it
> --- because man-in-the-middle attacks are real and you don't get what
> you think. This is why *trusted* distributions (Arch is *not*
> trustworthy) are best for beginners. Package managers are generally
> safe because they have built-in checks to make sure you received what
> you think you wanted. 
>
> FunFact: NPM (Node) had *nothing* checking against such attacks for
> more than a decade until the largest Internet worm in history happened
> because of it. This is one of the many reasons I despise Node and
> their reckless community.

After you have downloaded the script, and are convinced it is safe to
run (yes you should actually be that paranoid, all the time) then run
it by just typing `ws` from the command line. It is interactive. 

Accept the defaults when you first start, you can always change them later.

If nothing happens you probably need to add `$HOME/.local/bin` to your
`$PATH` (which unfortunately is still not a default on most systems even
though it is the standard from the [Open Desktop] initiative). You have
two options:

1. Use the full file path: `cd; ./.local/bin/ws`
1. Get help from someone to add `$HOME/.local/bin` to your `$PATH` safely

