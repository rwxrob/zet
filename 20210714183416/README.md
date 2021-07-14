# Annoyed at How Wrong the Kubectl Cheat Sheet Is

There's such an objective level of ignorance represented in the [kubectl
cheat sheet]() beginning with the simple fact that creating any alias
along for `k` just doesn't work with several very valuable Linux/Unix
tools. For example, one of the most valuable commands you would want to
use is `watch k get pods` but you just cannot do that with an alias. Not
understanding this remedial fact shows how little the people who made
the cheat sheet actually understand the UNIX/Linux way of doing things.
In fact, I keep running into this among people who profess to be DevOps
and Kubernetes "experts" and "infonauts." Fact is, their Linux terminal
skills are shit. This is why a single-line utility `exec` script is
almost always better:

```sh
#!/bin/sh
exec kubectl "$@"
```

Another reason is for all those who use Vi/m. By making `k` a command
you can to `k get pods` directly from within Vi/m and get the output.
That just doesn't work with an alias at all. Again, base ignorance on
the part of those professing expertise in the field.

Bottom line: there are a lot of Kubernetes and Cloud experts to don't
know a fucking thing about using the UNIX/Linux terminal, and yet the
Linux Foundation is a parent of the Cloud-Native Foundation. Don't be
one of these. Learn the foundations of terminal *first* then embark on
your cloud journey.
