# Get Git Submodules After Forgetting `--recursive`

It's a typical thing to forget. You did your `git clone` but forgot to
add `--recursive`, now what? Turns out it's not that hard: 

```
git submodule update --recursive
```

Hell, I might even make that an alias for `update` or `git update` but
then I'd just forget it again.
