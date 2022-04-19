# Bork `kubectl` Config is So Fucking Brain Dead

Just lost a lot of coding time when I did a `kubectl config set-context`
only to realize that is *overwrites every fucking entry in
`~/.kube/config` unnecessarily*. I added some `oidc-provider` sections
in there (rather than creating and managing an external file that would
confuse end users) and `kubectl` just blows everything the fuck away.

That is just so stupid I don't have words! There is absolutely no reason
to do that unless you are a lazy developer. I don't buy the "but we need
to avoid conflicts in the future" argument. I know that because *good*
developers (like Ben who wrote `kind`) do not do that. The respect what
is already in the file (which, incidently is the best part about
`yaml:",inline"`).

The problem is that no developer should ever assume they can just
completely destroy a configuration file and rewrite it the way that they
want. It is very common for people to add non-conflicting configuration
data to that file. The only fix for this is that I know have to maintain
yet another file in some place I can never be sure `kubectl` won't
decide to overwrite later as well. The more I work with Kubernetes
source code the more I fucking hate it.

    #k8s #rants #kubectl
