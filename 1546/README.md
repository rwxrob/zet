# K8SAPP Gotchas: Helm Does Not Create Namespace

TL;DR; *always* use `helm --namespace` no matter what --- even when you think
you don't need it.

While analysing the differences between the Node Feature Discovery
Kubernetes application official installation instructions I uncovered a
fatal flaw in Helm's assumptions about namespaces when the `--namespace`
argument is not provided. 

But, what is worse, is that some templates will assume and inject a
`namespace: default` into your Kubernetes resource files when applying
them without you knowing --- particularly when dealing with things like
ClusterRoles.

Tags:

    #helm #cloud #fails #k8s
