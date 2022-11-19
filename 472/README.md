# K8SAPP Embraces Git Instead of Shunning It

One of the most annoying (and frankly stupid) design decisions of Helm
is discarding the world's best source management utility and replacing
it with tarballs. This is the source of much confusion and extra work
when people realize they still need a way to track all their
customizations and forks to inadequate templates. Had the Helm project
had the foresight to keep all "Charts" as repos this would all go away.
We could just fork a "chart" and make our changes and ensure upstream
changes are made over time. This is a tried and true process used by all
applications development for over a decade. 

A K8SAPP undoes what Helm has broken by flattening Helm charts into their
default Kubernetes resource YAML files and putting them into Git repos
for proper management.

Related:

* [20211115160539](/20211115160539/) Kubernetes Applications (K8SAPP) Management Conventions

Tags:

    #k8s #helm #tips #k8sapp
