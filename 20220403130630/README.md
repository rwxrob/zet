# I'm Fucking Done with JSON, YAML and Protobuf FTW!

While meditating after yoga today it occurred to me that most of my
problems when dealing with Go projects are because of JSON marshaling
because of how lame the `encoding/json` package is and how Go is
forever stuck keeping it. In fact, I really appreciate the stance of the
Go team even more about *not* putting things in the standard library
easily. Because one fuck up, like escaping angle brackets and equal
signs in JSON because of one fucking stupid ass edge case, will forever
haunt the library.

I've said it before, I was leery of using yaml.v3 before because of
Kubernetes obsession with staying on yaml.v2, but the more I read the
Kubernetes source code the less respect I have for the people on that
team making the design decisions, at least in terms of Go coding. It's
almost like a bunch of Java people learned Go in a cheap bootcamp and
then make all the core Kubernetes software (because apparently that is
largely the case). Kubernetes was written mostly by life-long Java
programmers, and you can really fucking tell. So, why the fuck would I
care about their position on yaml.v2? I just don't.

There's one exception, however, Ben, the author of Kind. He seems to
have more of a clue than most. And, he used yaml.v3. It's because of him
that I know can leverage the nearly unknown amazingness of
`yaml:",inline"`. Just that alone has be permanently sold on YAML over
JSON. You just cannot do anything like it with *any* JSON library.

Sure I'll have to use JSON on occasion and work with it. But for
anything that I control, it's yaml.v3 and Protobuf all the way.
Honestly, YAML is far better for configuration files (JSON is horrible
for that) and when I do need fast marshaling over the wire there's
nothing (in the mainstream) better than Protobuf. That leaves JSON out
in the cold. It is getting phased out by so many projects its crazy.
When the web finally allows Protobuf/gRPC over the wire between sites
that will be lights-out for the boomer-era JSON schema. It actually
makes me laugh and cry a little that idiots are still considering
JSON5.

So bring on the haters. Yes I hated on JSON. I own it. It got us very
far and for that I'm grateful, but like God says in the Bible, "if ye
are lukewarm I shall spew you out of my mouth", and people, JSON is
lukewarm, it is neither high efficient as a network serialization thing,
nor is it any good at configuration files. In fact, the only thing that
JSON really did (for which I am immensely grateful) is save us from XML.
OMG, what the FUCK were we thinking?!

    #rant #json #yaml #xml
