# YAML Happily Overwrites Duplicates Without Error

This might seem like a good thing. It's not. It means that all of we
"YAML Programmers" out there have the shittiest parser to deal with
possible. It's not YAML's fault. After all, it's just a structured data
format, not a programming language. But Kubernetes (and the entire
cloud-native world) has come to treat it as one. You cannot hate on
`var` in JavaScript (and God knows I do) and not also call out YAML's
silent failures to catch reassignments/redeclarations that things like
`let` in JavaScript would immediately catch.

```yaml
some: thing
some: other



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
