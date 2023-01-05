# Don't Force Tag Updates for Go Projects

Ran into a rather critical problem the other day by using my `tag`
command to force an update to an existing tag. Doing so (obviously to me
now) blows up anything that has ever done a `go get` for that Go module
and has it in `go.sum`. So yeah, just don't do that. Be okay with more
frequent tagging (or don't tag at all forcing the pseudo-tags).

    #golang #coding #tips
