# It Appears Safe to Unquote `for` Shell Loop Var

The following is proof:

```sh
port='56 56 345 hello;ls;'
for p in $port; do
  echo "$p";
done
```

The `echo` obviously needs quotes. But it's not so obvious that `$port`
doesn't need them, and, in fact, can't have them if you want it to do
what it's suppose to do (split on whitespace or `IFS`).

Here's what `shellcheck` has to say:


