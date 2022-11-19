# Get scan.Pos() without Overhead

One of the biggest headaches and slow-downs of the first rune scanner I
created was that I thought I had to keep track of the human-readable
position during the scanning. That was really stupid looking back at it.
I had to rewind one rune at a time and go forward and such otherwise the
could of runes to bytes would be off and I'd lose any line numbered.

Seriously, what the fuck was I thinking?

The obviously easier way to do this is to just calculate the position
when you need it, at that final moment when you are actually printing
out an error or 10. You just save the byte position in the buffer and
scan all the runes again up to each of those points counting bytes, and
runes, and lines as you go. It's only a single additional pass through
all the buffer, which is already in memory, so there's virtually no
penalty on performance.

    #golang #coding #tips
