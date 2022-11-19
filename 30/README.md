# Use `realpath` to Get Real Path

Using `realpath` transforms a local path into a full one, or keeps the
same path if it is already a full path.

```
some -> /home/rwxrob/some
/home/rwxrob/other -> /home/rwxrob/other
```

This can be done in Bash without calling `realpath`:

```bash
if [[ $0 =~ ^/ ]];then
  echo "$0"
else
  echo "$PWD/${0//\.*\//}"
fi
```

POSIX shell cannot do this because it cannot examine just the first character of `$0` without calling out to a subprocess so might as well just use `realpath` for that.
