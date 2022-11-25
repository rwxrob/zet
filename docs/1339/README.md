# `isonan` When Your Need More Than `isosec`

As perfect as `isosec` is for uniquely identifying things in a
human-friendly and creatable way, sometimes you need some help from the
computer to get even more precision. I call is `isonan` which is simply
the nanosecond in addition to the second. Nothing fancy, just the way I
like it, simple.

```sh
#!/bin/sh
exec date -u +%Y%m%d%H%M%S%N "$@"
```
