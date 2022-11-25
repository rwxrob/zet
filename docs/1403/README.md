# Design Flaw in `kubectl` Forces Upgrade

While deploying my `klogin` tool at work one of the users opened a bug
on it stating that "it should not force an upgrade of `kubectl` unless
the user agrees to it" but it turned out that it was being triggered
from my calling `kubectl config get-contexts` at the end of the login
process. So far we have never seen this on our production jump boxes. My
theory is that if `kubectl` cannot phone home that it just silently
ignores the autoupdate, but I now know for a fact that it *will* do an
autoupdate if it can on a persons personal laptop (because it happened
to someone who reported it).

If the `kubectl` project does not have a 100% backward compatibility
assurance --- and I'm quite certain they do not --- this is a critical
design flaw. Just the other day someone was asking me the best
enterprise architecture to deal with vendors locking down cluster
versions, if having multiple clusters was a good architecture, and the
fact is, it is going to be mandatory the way things are going. It will
be very possible to have not just more than one cluster that must be in
a KUBECONFIG but dozens, maybe even hundreds eventually. As Kubernetes
continues to expand, and as a cluster becomes more akin to a "server"
today, we are going to see the assumption that one `kubectl` can handle
all of them dissolve into oblivion.

This is the kind of fatal flaw noob architects and short-sighted
developers make *all the fucking time*. They don't think about what
happens in five years, what if everyone did it. This is how we got
fucking Electron bloat out of control. This is how we got embedded
full Eclipse engines (not just embedded JVMs, which was bad enough). How
this shit makes into enterprise scale deployments is an absolute mystery
to me.

I need to open a bug on `kubectl` but I don't know if I have the
patience to defend it and school these idiots on why this is such a
fucking bad idea.

Have I mentioned how much I'm souring on the entire Kubernetes thing?
Nothing destroys my confidence in a product or initiative more than
getting dirty in the code and seeing what shit it is.

    #kubectl #bug #k8s
