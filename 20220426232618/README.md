# Mim KEG Publisher Will Use Go `rsync`

Been thinking a lot about the best way to publish KEG sites to the
Internet. Seeing how a KEG site is just a directory with files in it of
a particular format and order, it is a no-brainer to use `scp` and/or
`rsync` as the method of publishing. Sure you can save the content in
GitHub if you want, but that should never be a requirement in the end.
In fact, KEG data doesn't fit the Git model very well. We don't care
about revisions over time so much as we do the current state and if
there has been any changes since the last time. When something is
deleted, it should be *actually* deleted and not lurching in a previous
commit someplace.

All the searching anyone could ever want to do should be built into the
system itself, even pre-indexed so there is very little code needed to
*consume* the KEG site data (even though it will take a bit to crunch
the data into that form every time it is changed).

> Note that I will be using my `z` command instead of `mim` and
> composing the `mim` Bonzai branch into my `z`. Mim will be the name of
the tool that has only those parts in it related to Mimir™ Personal
Knowledge Management Assistant.

There are several pure Go implementations of `rsync` (yet another reason
to love the Go community).

    #mim #rsync #keg
