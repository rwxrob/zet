# What does `vic` do?

📺 <https://youtu.be/_KwufzorZlI>

It is the same as the following:

```
$ vi `which foo`
```

I just have it as a script:

```sh
#!/bin/sh
cmd=$(command -v "$1")
test -n "$cmd" && exec vi "$cmd"
```

