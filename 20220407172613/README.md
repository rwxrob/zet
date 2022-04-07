# Fastest Time to Productivity

I spend a lot of time focusing on developer and operator productivity. I
want to be up and running with all the power I need as fast as possible,
and with as few dependencies on external things also as humanly
possible. I suppose it's the hacker in me that drives these decisions.
It's definitely not the way a software engineer tends to thing, or an
academician with their emacs, or a machine learning person, but they can
all stand to benefit from the result.

There are three up-and-running scenarios:

1. Monolith of tools (like a rats nest)
2. Terminal-centric development
3. Cloud native infrastructure engineering
4. Max hacking

The first one can be entirely done with a `z`-like Bonzai monolith. Not
even a terminal is needed since a simple REPL can be built into it.

1. Install `z` binary

The second needs some extra binaries installed, but would work on any
system with a VT100-compatible terminal on which these apps can be
installed. The best example of this is on a Mac or Windows machine:

1. Install a terminal (MS Terminal, iTerm2, Alacritty, etc.)
1. Install `bash`
1. Install `vim`
1. Install `tmux`
1. Install `lynx`
1. Install `git`/`gh`
1. Install `z`
1. Run `z setup [all|bash|vim|tmux|lynx|git]` to configure above

The third caters to those who are required to use a Mac or Windows
machine due to company or other policy. This requires a virtual machine
engine:

1. Install VirtualBox or VMware
1. Install (Headless) Ubuntu Server Linux
1. Install `vim`
1. Install `tmux`
1. Install `lynx`
1. Install `git`/`gh`
1. Install `z`
1. Run `z setup [all|bash|vim|tmux|lynx|git]` to configure above

> No WSL2. It's buggy and broken. I found out the hard way.

The fourth is when you have full control over everything that you use,
for example, as a professional or private hacker:

1. Install your favorite Linux Desktop Distro (Kali, Arch, Debian, etc.)
1. Install `vim`
1. Install `tmux`
1. Install `lynx`
1. Install `git`/`gh`
1. Install `z`
1. Run `z setup [all|bash|vim|tmux|lynx|git]` to configure above

The pattern is really the same on the last ones. The main thing is
bundling all personal application setup and configuration files into the
`z` binary for setting up immediately on *any* system.
