# Big Compatibility Problem with yaml.v2

While writing the `y2j` Bonzai branch I used yaml.v2 to first convert
everything using the `yaml:",inline"` trick only to discover that that
marshaling of it is incompatible with the core `encoding/json`
marshaling API. I don't have the error any more, but it had to do with
`map[string]any` and `map[any]any`. I was *really* frustrated because it
completely tanked my approach in `y2j`. For the hell of it I change v2
to v3 and, boom, it just worked, all of it.

Suffice it to say, from that moment on I was fucking done with yaml.v2.
I don't give a shit that Kubernetes may (or may not) be stuck on yaml.v2
for whatever dumb-shit reason. The more I read the K8S code base the
less impressed I am with the design decisions over there. But what does
my opinion matter, I just want my `y2j` to fucking work, and v3 fixes
it. The end.

Okay, another thing, v3 also has a reasonable indentation instead of
defaulting all arrays to not be indented. Sure that makes for less
nesting, but I've found (and I imagine so did they) that healthy 4-space
indentation is a good way to keep your YAML from getting really fucking
crazy. Make another file for god sake. Well, now that v3 defaults to
that larger indentation everything in my YAML life seems to have gotten
better. Plus the creator of Kind uses it. Ben gets it.

    #golang #coding #yaml #rant
