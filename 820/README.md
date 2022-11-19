# "Dedicated Kubernetes Clusters" are a Thing

I'm continuing to hear rumblings about applications requiring their own
"dedicated Kubernetes clusters" and thinking to myself, "Didn't we go
through this with Java JVM and Eclipse 'runtime' tech?" If an
application requires it's own  cluster then what is the point of
Kubernetes in the first place? Vault suggests exactly this. I wonder if
this is because of the scope and criticality of Vault. If some other
controller goes bad then all the corporate secrets in Vault would be up
for grabs, but still. The big take away here is that if Kubernetes is
truly going to continue to take off (as it has) that multi-cluster is
definitely the future. Getting clusters to talk to each other and
considering them more like individual "servers" in the old days with
"processes" on them is very much the preferred paradigm for IT
architecture. There's going to be a ton of cluster-to-cluster
communication stuff that will emerge in the next few years.

    #k8s #architecture #multicluster
