# Kubernetes Has Forever Forked YAML Keeping v2

Just read about how the `go-yaml/yaml` people broke Kubernetes by making
a stupid decision to add formatting that wasn't there before breaking
every Kubernetes app and service that uses it. Now I have a decision to
make: do I use the broken v3 because it is more modern, or do I use what
Kubernetes does and hitch my wagon to their library instead?

One thing is for sure, Kubernetes will *not* be going with v3 ever if it
doesn't want to break everything it already has.

I think that is reason enough for me to use the Kubernetes (v2) YAML
library and stick with what it does when it upgrades. Plus there are a
number of utility functions there as well.

* Revert v2 line length change as discussed in \#670 · go-yaml/yaml\@7649d45 · GitHub  
  <https://github.com/go-yaml/yaml/commit/7649d4548cb53a614db133b2a8ac1f31859dda8c>
