# Bonzai, Freedom from Fear to Explore

What is my #1 reason not to use any of the one-off tools out there, you
know, the fuzzy-finders, the better versions of find, the prettier `ls`
variations? Why do I so chafe against all these efforts? If you know me,
you could say it is is because all of them are fucking irrelevant
distractions from learning real-shit that you need to master to do most
hacker/operations jobs. Those cutesy tools (usually unnecessarily
written in Rust, my god the fucking pain of writing ls in Rust, lol) are
complete fucking wastes of time because there is zero chance any of them
are ever going to be on a system you don't have full control of, and
guess what, that doesn't describe *any* work environment. But there's
hope of a new dawn, a Bonzai sunrise.

See Bonzai addresses the lack of portability and irrelevance problem as
the first and foremost design consideration of them all: composition.
Had all those shitty tools been done as Bonzai branches not only could
each and every one of them be used independently, but they could also be
composed into a single multicall/monolith that can be copied to any
system with a single `curl`/`scp` command. That's the power of Bonzai.
That's the freedom Bonzai provides.

Why do I care? Because now that exploration into what a better `ls` tool
(without all the shitty dashes) might look like is completely and
totally acceptable, no fear of creating yet another irrelevant tool that
has no chance in hell of ever getting on a production system, ever. But
a single Bonzai monolith only needs one thing: permission to copy a
binary executable into my own home directory (or pod) on the system.
That is all. I can bundle every crazy ass exploration into my monolith
and hack on it when I have time. But what's even better is that I can
dynamically share all my explorations as Bonzai branches with the whole
fucking world. So all that collective development effort goes into
improving everyone's life in *very real ways* because now they can take
it with them into the work place, or into a rat's nest, or wherever the
fuck they want it. *Everything* I need can be created and compiled into
a single binary, yes, even `vi`, `tmux`, and `lynx` eventually (or at
least better versions of them).

Here's the thing, I would never have been motivated to rewrite `tmux` or
`vi` or `lynx` before. Just more wasted effort on something that I'd
have to install every time I wanted to use it. But, the prospect of
adding these core tools that I use constantly into my
one-monolith-to-rule-my-world is *very* compelling. In fact, it's so
compelling I'm actually thinking of porting the popular Rust tools into
Bonzai branches just to show how superior Go is to Rust (if for no other
reason). Hell, I could even put an entire fucking terminal emulator into
a Bonzai tree. I'm not even kidding. We could port all of Alacritty to
Go, a bit slower perhaps, but good in a pinch *because I only have to
copy over a single fucking binary*. Fuck Docker. This is *way* more
compelling for hackers and ops tool-smithies, the blacksmiths of the ops
and hacker world.

So, which shitty Rust tool can we port to Bonzai first? It will take
probably 1/5th the time it took to write it.

    #bonzai #rants #tools #linux #opsec #hackers
