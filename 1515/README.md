# Remove a Git Submodule

Assuming you have a submodule named `foo` in the root of your repo:

```bash
git submodule deinit -f -- foo
rm -rf .git/modules/foo
git rm -f submodule
```

If that was the last or only modules you can also remove `.gitmodules`:

```bash
rm .gitmodules
```

Then just commit and push as usual.

If for some reason you have your submodules in subdirectories then add
the relative path to the subdirectory in front of the submodule name
(`path/to/foo`).

    #git #tasks
