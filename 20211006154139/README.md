# Use `jq -s ` to Combine Multiple JSON Objects

It is not uncommon to have multiple JSON objects in a single file, or to
want to deal with several separate files as if they were all in the same
JSON file. This is why `jq -s` (slurp) exists. Adding the `-s` will
automatically create a top-level array containing all the objects in the
order that they are parsed. 

This is useful when you have a log of JSON entries, one compressed JSON
object per line.

This is also particularly useful for combining multiple YAML files into
one when combined with the Go `yq` program. In my case, I've made the
first YAML document (within the single file) the meta data, like a
section, then the rest of the documents are each objects of the same
type, like a meta-level array with clean separation between each of
them.

```
# fetch only the meta data
yq e unix.yaml -j | jq -s '.[0]'
```

Tags:

    #json #jq #tips #yaml
