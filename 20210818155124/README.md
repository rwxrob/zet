# Use `jq .[] | select` and `test` to Filter

The more I learn about `jq` --- and see its use in the field --- the
more I realize it is by far the most important utility of the modern
cloud era. *Everything* is JSON these days (even though you might think
it is YAML). Even ProtoBuf ultimately ends up as JSON when being parsed
and queried from the command line. In short, `jq` is `sed` and `awk`
combined for anything with JSON. A lot of people know how to use basic
`jq` for regular things like looping through data, but only recently
I realize that an entire 20 line shell script I wrote some months back
to filter some resources with different labels could have been done in
one very powerful `jq` line. I'm never making that mistake again.

We have a label on all our namespaces at work called `nstype` which is
set to `user` or `system` depending on the type of namespace, pretty
typical stuff. Here's the one line command to show all `user` labels:

```bash
k get ns -o json | jq -r '.items[].metadata | select (.labels.nstype == "user") | .name'
```

That's all it takes to get a perfect, one-column list. To change to
`system` just change `"user"`.

Direct matching is cool and all, but when you combine this with `test()`
regular expressions (PCRE, or course) you realize this is all that you
ever need. Say goodbye to `awk` and `sed` for this kind of stuff.

Here's an example of everything that starts with the letter `r`:

```bash
k get ns -o json | jq -r '.items[].metadata | select (.labels.nstype == "user") | select(.name|test("^r") | .name'
```

Which you could have also done exactly the same way with just `grep -P`:

```bash
k get ns -o json | jq -r '.items[].metadata | select (.labels.nstype == "user") | .name' | grep -P ^r
```

It's just nice to know you have everything you need in `jq`, which
really doesn't violate the UNIX philosophy with all this. It's "one
thing" it does well is handle JSON, and it is by far the best at it.

    #json #jq #tips #devops #coding #shell #bash
