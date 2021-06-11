# YAML Happily Overwrites Duplicates Without Error

This might seem like a good thing. It's not. It means that all of we
"YAML Programmers" out there have the shittiest parser to deal with
possible. It's not YAML's fault. After all, it's just a structured data
format, not a programming language. But Kubernetes (and the entire
cloud-native world) has come to treat it as one. 

You just can't hate on `var` in JavaScript (and God knows I have) and
not also call out YAML's silent failures to catch
reassignments/redeclarations that things like `let` in JavaScript would
immediately catch. Is it the specifications fault or the tool? Really
doesn't matter to the engineer at work who just had `name` overridden
and deployed it that way (which I caught looking through some YAML to
get ideas on how to do my own). You can't blame the person, the
duplicate was literally on a full two screens down. 

```yaml
some: thing
some: other
```

And, by the way, `yq` is seriously broken on this:

```
$ yq e . /tmp/foo.yaml
some: thing
some: other
$ yq e .some /tmp/foo.yaml
other
$ yq e '.some[]' /tmp/foo.yaml
# nothing
```

I've not really been impressed with the `yq` internals for some time now
and added to my wish list of things to redo. The better effort would be
to add simplified YAML parsing to the `jq` core library and enable an
option to catch these things, because it looks like JSON has the same
problem.

```json
{"some":"thing","some":"other"}

{
  "some": "other"
}
```

> 💢 YAML whitespace dependency is just an absolutely shitty design for
this production deployment stuff. It's seriously fucking horrible. It is
actually an anti-pattern to put all your production systems behind 300
lines of two-space indented YAML bullshit. It will die. Mark my words.
Within five years another format will emerge for all of this. Perhaps it
is TOML's time to shine.

