# Grep in Bash Without the `grep`

We don't need no stinking `grep`. Here's an example of "grepping" for
everything in the current direction that begins with `RE`:

```bash
while IFS= read -r line; do
  [[ $line =~ ^RE ]] && echo "$line"
done < <(ls -1)
```

You can easily throw this into a function and never need a sub-process
ever again for this kind of stuff.

    #bash #scripting #tips #grep
