# Advantage of Smaller Bonzai Base Package

It might be immediately obvious to everyone else, but as I was updating
all my stuff that depends on the `bonzai` package to the latest
(v.0.9.0) it occurred to me that not only does everything not
necessarily need to update to the latest bonzai package every time, but
that some monoliths will eventually have several binary copies of
different versions of the bonzai package in them. This is the most
significant downside of Bonzai that I've encountered so far. It's
nothing to worry about for most, but it is definitely worth
consideration. Let me explain.

Say you have a monolith with a dozen or so imported Bonzai branches.
Imagine each one uses a different version of the bonzai package, which
isn't too hard to imagine because why on Earth would people update their
branches unless they need the new stuff provided by the new bonzai
package point release. So, worst case scenario, we have a dozen branches
with a dozen different versions of the bonzai package, now we have our
own monolith tree at the latest, making that the very unlucky number 13.
That means the resulting binary will have 13 times the size of the
compiled binary for each bonzai package version. Remember that 1.8 MB
monolith `z` command you use? Now it's more than 10 MB for no reason
other than everything uses a different version of the bonzai package,
and that size cannot be reduced through any optimizations.

So let's say that over the course of two years there are 10 different
bonzai package releases and you have gathered a ton of branches from
different members of the Bonzai community. Without even considering the
raw size of the branches you are gathering (some like `web`, a `lynx`
replacement, and others could be very large themselves) you now have
potentially 10 times a couple dozen branches. A rough estimate would be
that you will use something like 250 MB for your monolith. That seems
like a lot, relatively, but consider that a single Electron applications
immediately burns 2-6 GB of RAM all by itself. As I said, nothing to
worry about, unless you are making very small binaries that you want to
fit on smaller devices. It's just a reason to remember to update Bonzai
branches you control to the same version so that you can avoid it.

This also means that I must remember to *always* keep the core bonzai
branches (`help`, `conf`, `vars`, `compcmd`, `compfile`) on the same
bonzai version no matter what.

    #bonzai #golang #coding #tips
