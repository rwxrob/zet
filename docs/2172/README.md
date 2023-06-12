# Use `set -C` at beginning of bash scripts

By explicitely setting noclobber you force yourself (and anyone supporting that bash script later) to force clobbering any files. This makes it easier to sleep at night knowing your bash code is in production. Using the `-C` instead of `-o noclobber` allows it to be combined with other single letter options (like `set -Cex`).
