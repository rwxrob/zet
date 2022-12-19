# Bonzai dilemma of separate package libs from commands

I've hit a not-so-serious conflict in the conventions I've set up to deal with Bonzai stateful command trees.

In the natural organic method a single repo (ex: `keg`) is created to contain the high-level functions (ex: `keg.go`) as well as the commands that encapsulate them (`cmd.go`) and an actual stand-alone command (ex: `cmd/keg/main.go`). This works fine for most of the live of granular command branches, which is the entire point. But sometimes a reason to break out the high-level functions into an API repo of their own manifests itself (as it has with `keg-go`). There are two main reasons for this:

1. Dependencies need to be minimized
2. Frequent changes to command branch

I have noticed, for example, that making even a slight documentation fix to the `keg` command triggers a full version upgrade in order to inform people that the version has been updated. The one-to-one correlation between the `Version` in `cmd.go` no longer makes sense since the version to the core API high-level functions and model hasn't changed at all. This is an obvious case for putting the API functions into `keg-go` and creating a dependency on that package from the `keg` stateful command branch package.

But what do name them?

I initially tried `libkeg` but that just didn't sit well. So I went with naming the packages the name, and keeping the git modules separated by adding the `-go` to the end of the one that implements the importable high-level API. As it turns out, the `keg` command branch doesn't have a conflict at all since it isn't importing itself, ever. Even the unit tests work. And when and if I ever do have a conflict, I can always use `import` prefixing (as I do for my `fs` package).
