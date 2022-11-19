# Use `select` with `startswith` for `jq` Filters

The `jq` command is amazing, but sometimes not particularly intuitive.
To select all the objects that have a field with a particular prefix is
one example:

```sh
jq '.[] | select(.name|startswith("rwx"))' images.json
```

There's also an `endswith`. I noticed that `select` is usually what I
want (and not `map`) because I still want the entire object that
matched. This allows an equivalent of piping `grep` to another `grep` to
reduce down to only what I need.

    #jq #json #tips
