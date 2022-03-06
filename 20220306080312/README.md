# Unlocking the Default GitHub Branch

I've often been foiled trying to rename branches and do stuff with the
protected default one (say when changing `master` to `main`). Here's the
command to "unlock" it:

```
git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/main
```

