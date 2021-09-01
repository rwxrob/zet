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

    #k8s #gatekeeper #opa #policies #sites #learning
