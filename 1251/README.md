# Use Version in Package Import Name in Go

Just noticed a very peculiar thing in the `yq` module. It has a `v4` in
the import line as if there were an different directory within the
GitHub repo. After a few minutes of "wtf"-ing I found this import line
in the `go.mod`:

```
module github.com/mikefarah/yq/v4
```

That's right. Mike is just fucking around with the import module
declaration and apparently that works.

Is that a best practice?

I really don't know. I do like that this frees a person from using
`gopkg.in` like the YAML project does. But am I willing to do that all
the time now? Not really. The entire premise of this is that you have to
do it all the time. But isn't that the entire point of the git related
versioning system? I really don't know. But I'm just not going to do it.

    #golang #coding #tips
