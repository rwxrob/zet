# Mimir™ Personal Knowledge Management Assistant

With the Boost coming up next week I want people to know that I
seriously need and want help doing the FOSS development on several
significant projects so that people can answer the question "What should
I work on?" rather easily.

Mimir™ (`mim` for short, named for the Norse God of knowledge) will be
the product I've been planning for years at this point. It will have
everything needed to get funding, but it will remain 100% open core as a
business. Eventually, I'll seek FOSS funding for it and see if I can get
enough seed capital to hire a full (but small) team to work on this
stuff full time (probably from among my Twitch community). If not, I
will definitely be putting our \$100+ bounties on specific things I need
coded.

Mim™ will really just be a Bonzai™ branch composing the following
branches (which could also be grafted into any other branch out there:

* `zet` manage *zettel nodes* of messy, brainstorming content, PKG stuff
* `lab` - manage *lab nodes* of messy exploration, and workthroughs
* `info` - managing *info nodes*, tagged, <380 characters
* `keg` - manage *master node* subs and sharing, knowledge exchange grid
* `live` - manage live streaming and sharing integrations (Twitch, etc.)

Some of the usage will look like this:

```
mim keg serve - serve keg site content to whatever, and pair
mim keg sync - explicitly push/pull your local keg site (rsync, etc.)
mim live message <some thing to send>
mim zet create <some optional title>
mim keg search <query for your keg site and all those to which you sub>
```

Like Git repos, every KEG site will be an autonomous, independent,
identical backup to the one that is being managed. More importantly, ssh
connections will be established between KEG servers so that changes to
*any* site replica will automatically replicate (depending on
configuration). This will provide outstanding sustainability as well as
the potential to have the same site redundantly maintained in a dozens
places on the Internet and elsewhere. This also removes the need for
centralized failures like CDN providers because a `mim keg` user can
essentially create their own CDN. I'm even going to automate the
round-robin backup to several USB sticks mounted to any endpoint. Grab
one and I have *everything*.

Everything will have Bonzai shortcuts and aliases to make it
simpler to type.

Of course, the entire thing is built on the foundational Bonzai™ FOSS
project, which may or may not be umbrella-ed under the Mimir company.

    #mim #bonzai #pkg #zettelkasten
