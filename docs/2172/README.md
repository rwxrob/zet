# Use `set -C` at beginning of bash scripts

By explicitely setting noclobber you force yourself (and anyone supporting that bash script later) to force clobbering any files. This makes it easier to sleep at night knowing your bash code is in production. Using the `-C` instead of `-o noclobber` allows it to be combined with other single letter options (like `set -Cex`).

***However***, if a program clobbers/overwrites a file (such as the following) there is nothing that `-C` can do to prevent it. In such cases, explicitly checking for the file is safer. Some might argue that this means it is unwise to ever trust `-C` since it might make one lazy and not check in such cases.
