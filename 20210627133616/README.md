# Host Golang Modules on GitHub

I hate to have to say this, but I can think of a few more reasons that
GitHub is the definitive place to host your Golang package modules if
you want people to actually use them on projects where you work for any
enterprise of significant size. I may not like these reasons, but they
are just the facts today. Some of these reasons have become *really*
apparent now that I've been working in a large, conservative enterprise
for a while (again).

## Businesses Trust GitHub

I have my issues with GitHub --- especially after they abruptly pulled
my educational status of SkilStak (after 7 years without a problem) ---
and gave me 30 days to get my stuff off (which I still only have on my
hard drive here, which terrifies me). But the reality is that GitHub is
trusted by every large organization I have run across. Being run by
Microsoft is a good thing to them. It means stability. It means they
expect GitHub to keep them safe and cozy, and to a large extent GitHub
has followed through on that. This is one reason that GitHub Enterprise
is *destroying* GitLab in the market (that and `gh` CLI tool).

This also means that the `github.com` domain is almost guaranteed to be
okay with your HTTP proxy setup. So yes, `gh` and everything else will
just work. Had I setup my own Gitea on my own domain there is no way
that would ever be authorized. Vanity domains seem like a good idea, and
Go caching servers ensure that they are just as safe as everything else,
but they are a sure way to get *all* your content blocked from most
conservative enterprises including school districts. That alone is
enough to keep everything on GitHub, or at least a secondary copy of it.
Let me say that again, if you host on *anything* but a major domain you
are likely *never* going to be able to use your Go code in any projects
you do for that enterprise. That's a big fucking deal. 

By the way, this is the same reason you should always use Apache-2 even
if you don't like it, because it is by far the most trusted license by
enterprises. You might not like it, but if you want to use your FOSS
projects at work, you don't really have a choice.

## GitHub has the Most Active Community

I love the `cview` project, but no one knows about it, which is really
unfortunate because it has *way* more stuff than `tview` (which it
forked some years back). Trevor has taken the project onto his own
private servers, which now means that I cannot use it for the reason I
just described (domain is untrusted within the enterprise that I work)
and frankly there is no way to get visibility to the ongoing changes to
it. 

I really respect his position on moving everything off of the big
corporation Git hosting services. He has his reasons. But he has just
completely guaranteed that no one ever uses `cview` in those
environments and frankly he either doesn't know or doesn't care. But
what is really sad is how many people just are never going to hear about
it.

At first I was tempted to fork it again and put it all back on GitHub
just to give it visibility and be able to use it. But that is just too
much work to keep up with the upstream changes in everything that is
involved, plus it would probably piss Trevor off. Who knows? But for all
those reasons I'm not even going to bother and neither would most others
with full-time jobs. We have too many other things to work on of our
own. So GitHub, unfortunately, wins this one as well.
