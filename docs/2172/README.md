# Use `set -o noclobber` at beginning of bash scripts

By explicitely setting noclobber you force yourself (and anyone supporting that bash script later) to force clobbering any files. This makes it easier to sleep at night knowing your bash code is in production.
