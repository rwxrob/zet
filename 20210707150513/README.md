# Use `k` Script for `kubectl` Instead of Alias

Once again, aliases and functions have burned me. Initially, it seems
like a good idea to add the following:

```bash
alias k=kubectl
```

Then you try something like this (a *very* common command):

```
$ watch k get pods
```

Which produces a `sh: 1: k: not found` error for obvious reasons.
Suddenly, you immediately regret your decision, so perhaps you try it as
a function.

```bash
k() {
  exec kubectl "$@"
} && export -f k
```


