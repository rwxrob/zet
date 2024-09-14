# Mac doesn't know where GOOD bash is

I fucking hate writing `#/usr/bin/env bash` in anything but ...

```
$ /bin/bash --version
/bin/bash --version
GNU bash, version 3.2.57(1)-release (arm64-apple-darwin23)
Copyright (C) 2007 Free Software Foundation, Inc.
__ps1
git branch --show-current 2>/dev/null
hostname
```

That's right. Doing a `brew install bash` only puts it into `$(brew --prefix)/bin`. I really hate that this encourages use of `#/usr/bin/env bash` idiom.

This leaves me with the very unpleasant option of writing any and all shell scripts as POSIX/ksh which has the advantage of also working on anything with z-fucking-shell. God, I hate that I have to give up all the power and security of bash for that shit, just cuz Mac. It also really fucking pisses me off that Apple just won't update their version of bash because of licensing issues. Cowards.

This whole thing really has me leaning toward making a monolith (my `z` command) for everything that I want to combine together. It's a lot cleaner that a shit-ton of shell scripts anyway.
