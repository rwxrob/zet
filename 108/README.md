# Use `go work ...` for Concurrent Go Package Dev

The new `go work` tool in 1.18 is yet another amazing part of this
monumental release. It takes some getting used to, but it really isn't
that complicated. As a rule, just to the following when you create a new
project (or need to work on an existing one):

1. `go work init` - creates `go.work` file
1. `go work use .` - so example tests work
1. `go work use ../<whatever` - package deps you are working on 

I repeat that last step for every package dependency. It doesn't hurt.
If it is there it will use it, if not, not.

You actually *want* to save this `go.work` file with your repo. It only
kicks in if those packages at those locations are actually at those
places, which they only would be if you are working on them as well
(usually).

There are a number of things you can do with environment variables, but
you don't really need to bother at all. It just does what you want most
of the time.

    #golang #coding #tips
