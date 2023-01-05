# Found github.com/cli/go-gh, but Meh

Got a little excited to see `go-gh` but then realized it just calls out
to the `gh` command rather than allowing you to create your own single
binaries that include the `gh` functionality. The GitHub team really
missed a great opportunity to expose a high-level API (not web API) but
instead opted to architect the `gh` command with mostly private
functions and structs. Had they put a little more thought into their
design they could have allowed developer integration at a much higher
level. But I doubt they even understood those last three sentences at
all, which is really just a shame. Short-sighted API design drives me
fucking insane --- especially when I'm forced to do it myself. I'm sure
they were under the gun and just put it off for later. Now we have a
super silly "wrapper" for *another* executable. This is fucking Go,
people, not shell.

    #golang #rant #github #cli
