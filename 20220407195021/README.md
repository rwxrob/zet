# Should I do a github Bonzai Branch?

I'm really feeling conflicted at the moment. If I were writing a shell
script it wouldn't be that big of a deal. I'd bang out the `curl`
request and more it into my `gh` config eventually. But now that I'm
putting everything into Go Bonzai branches I have a lot more options,
too many options. Theoretically, everything in `gh` can be put into a
Bonzai branch eventually. I'm not a huge fan of their interface. I do
like that they provided an interactive menu, but I don't like that they
still support getopt. I checked their interface and it works on Windows
and Mac pretty well. I need to make whatever it is into something that
is a part of Bonzai for anything easily. But that is all work. I would
need to factor out the menu prompts and get them into Bonzai, then
figure out which things I want a prompt for. I definitely need to do
that eventually. The fastest solution is to call out to `gh` and just do
what I do for shell scripts. But even then I would normally be adding
these custom commands to my `gh` config (like I did for `del` and
stuff). But the stuff I want to do related to pushing releases and stuff
does not fit into `gh`, so I already have to do my own thing. I think
the best solution is to just use the API directly from `json.Fetch` and
slowly move over the stuff from `gh` that I actually want to keep, but
in a way that is reusable. My biggest gripe with the `gh` tool is that
it didn't expose *any* high-level functions (like `yq` did) so there is
nothing I can factor out. It's all `internal`, which just convinced me
even more not to depend on `gh` for my own stuff. I'll steal what I want
out of it and do my own thing. That's the FOSS way. ;)
