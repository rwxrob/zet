# ZettelRepo Sizing Estimates

Luhmann's original zettelkasten had over 90,000 zettels in it filling 27
boxes, each with 2500-3500 zettels. But what would such a collection of
knowledge look like today in digital terms? I want to know because that
will influence decisions about indexing, computer memory, caching,
search optimizations and more.

Let's assume each zettel is approximately 42 lines of 72 columns, some
will be more, others less. Assuming only a few emojis (which are more
than a single character/byte) we can say a single zettel in digital form
will be about 3000 characters/bytes. Multiply that by 90,000 and you get
270,000,000 bytes just for zettels. That's roughly 256 MiB, one quarter
of a GiB.

Considering modern computers come with a *minimum* of 4GB RAM these
days. This is a pittance. Some gaming model skins are probably larger.
So I don't see a problem storing all of this in daemon memory
eventually. God knows we squander memory for much less important things.
I would link having your "second brain" available in memory for
immediate queries would be the epitome of computing power priorities.

In fact, we have enough room to not only store the full content of the
entire Zettelkasten, but also several specific indexes including an
every-word index. Even if we triple that number we are still *under* 1
GiB of memory.

Yeah, we are going to be fine. I'm excited.
