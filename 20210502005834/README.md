# Problems with `sed`

I really fucking hate `sed`. Here's an example of why. Compare the
following to the Perl standard:

```
echo "## Some Header" | sed 's/#\+ *//'
echo "## Some Header" | perl -ane 's/#+ *//'
```

It's just one character that needs to be escaped (the `\+`) but the
other `*` does not need it. This inconsistency is why people went
bat-shit crazy trying to use regular expressions with `sed` and `awk`
and all their different versions. It's the reason `perl` was invented in
the first place.
