# Python fails again, this time MkDocs

The selection of Python to implement MkDocs might have made sense at the time. But after attempting to render my 2056 node zettelkasten site and waiting for 260 seconds for it to build I realize that MkDocs is absolute shit simply because it chose to use the ridiculously slow Python language. A similar build in Hugo in Go finishes in 10 seconds. I thought it was broken at first, then I ran `strace` on the process and watching the fucking idiotic way that MkDocs handles parsing and indexing. It's SO FUCKING STUPID! OMG!

This is a devastating discovery. It means that MkDocs is completely and totally unsustainable for large knowledge bases. No one is talking about that because the average knowledge base that uses MkDocs is probably around 100 node tops. This means that MkDocs is *not* suitable for *any* enterprise knowledge base of any considerable size.

The worst part is that no one realizes this, no one is working on something that will *actually* work. There are over-complicated Hugo themes that attempt to do the same thing but have their own glaring issues.

I hate to say it, but this means that I'm going to have to make my `kn` tool do everything that MkDocs does even though I will *never* convince anyone at the enterprise level to use it because it will take a decade to get full-scale adoption. But I have no other option. I cannot wait around for 270 seconds every time I make *any* change to my site. That's right, MkDocs is so fucking brain dead that it rebuilds the entire fucking site rather than just the individual resources that have changed. It has no basic concept of when a resource/node was updated and whether it needs an update or not. This is such a basic requirement that *not* including it makes me realize how short-sighted the MkDocs designers are. I'm absolutely, positively *not* mentioning MkDocs in the upcoming Beginner Boost at all other than to say, *don't use MkDocs unless you never plan on building large sites again*. In fact, it's time to make a video and shout this discovery from the housetops before people migrate all their stuff to it only to discover they are stuck later. I cannot believe the lack professionalism of the MkDocs project at this point. A simple test at scale would have immediately revealed this show-stopping, unfixable design flaws. It's now part of my life's mission to ensure that *no one every uses MkDocs for any kind of substantial knowledge base ever again!*

This leaves me going back to my priorities as I had them. PEGN for the most efficient parsing possible, and some form of KEGML for storing the content. God I *hate* this when I try to do the right thing and adopt what the rest of the world is using only to discover that it is absolute, utter dog shit! And, yes, the entire world is enamoured with this dog shit and will remain so for another year or two until all their knowledge bases completely break because *MkDocs does not scale*! Just take a look at the completely STUPID `search/search_index.json` file to get an idea of what a complete fail the MkDocs design actually is. It's as if a bunch of remedial web developers decided to make a knowledge management system.

OMG! How the FUCK did I let myself NOT look at the code before adopting this SHIT! Now I'm on the hook for it at work and every place else I have put it.