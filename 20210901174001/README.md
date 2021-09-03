# Site: https://kubesec.io

TL;DR: It's like the `man` page system for OPA Gatekeeper policies.

This site is a golden find for anyone wanting to get their head around
what it takes to secure a Kubernetes cluster in their environment (CKS).
There are a ton of ready made OPA Gatekeeper policies that can be
dropped into whatever pre-validation you have before putting resources
into your cluster. We have it plugged into our own `deploy-chart` tool
that overlays Helm allowing us to make out own modifications to standard
Helm chart releases in a way that can be tracked.

Of particular interest is the verbose explanations of each of the
policies that are linked from above the Rego code explaining the policy,
so, when you go to install a Helm chart and do some pre-validation and
notice something isn't in compliance you can read about it specifically
and make the correct adjustments. I *really* love this because it
provides granular, layered learning about something that is otherwise a
huge topic to cover. There are hundreds of policies and they are all
searchable. 

Then again ...

If you are a hacker wanting some fresh meat in the cloud, these policies
are some of the best explanations of Kubernetes vulnerabilities ever
collected. 

Just take resource limit DOS attacks, for example. If you want to really
ruin someone with a Kubernetes cluster's day, target their application
to spawn too many of something with too great a size, chances are they
don't have the `containers[].resources.limits.*` policies in place.
Boom.

I'm certainly not advocating destroying enterprise clusters with DOS
attacks against dumb-shit CN applications written by inexperienced cloud
developers who don't know about constraints, but knowing how *not* to be
a victim can certainly come in handy.

    #k8s #gatekeeper #opa #policies #sites #learning
