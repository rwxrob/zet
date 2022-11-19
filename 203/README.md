# Always Read the Helm Chart Templates

Helm gets described as the "package manager for Kubernetes" all the
time, but this is a very dangerous comparison. When most people thing of
"package managers" they thing of things that seamlessly and safely
install software they need that they can always remove later. This is
simply not true for anything installed with Helm. While it is true that
you have to install stuff from package managers generally with root
access and are required to trust the organization that is allowing the
package to be released, you have have zero guarantees that a given Helm
"application" will not destroy your system without careful examination
of what it does.

This is because so many Kubernetes clusters are different. Nothing is
homogeneous at all. Perhaps one day we will get there, but we are not
there today. Say, for example, you just want to put JupyterHub in your
Kubernetes clusters for all your users. The default (currently 1.0.1)
chart will include something called a `continuous-image-puller` pod that
is a DeamonSet, meaning it will start up one *on every single node in
your cluster*. If you just blindly use the defaults for that Helm chart
(thinking like you are using `apt install` or something) you end up with
potentially thousands of daemons, one for each node. That's just
unacceptable in most cases. Maybe it is fine if you are deploying a
single cluster explicitly just for JupyterHub (a multi-cluster approach
that is getting more popular all the time) but not in any other case
where there are several applications all running in the same cluster.

The solution to this is to make sure you pull down the Helm charts
(which are Go templates) and read every fucking line of every fucking
one before you choose to use that particular chart. This will also give
you much better insight into the Helm values you will need to pass. In
fact, it was by looking at the template itself that I was able to
identify the exact parameter needed to disable the "puller":

```go
{{- if .Values.prePuller.continuous.enabled }}
{{- include "jupyterhub.imagePuller.daemonset.continuous" . }}
{{- end }}
```

Reading about this in the values helpers did not really definitively
answer the question, "What turns these things off?" This made it clear,
however.

Another thing you might want to know about is any ClusterRoles that are
being added. These don't show up in the usual `k get all` and such so
you might not even be aware that your Helm install has altered the state
of your overall cluster, not just the stuff in your application namespace.
