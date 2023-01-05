# Distributed Consensus Algorithm etcd Limitations

Since etcd is based on RAFT (a distributed consensus algorithm) it
absolutely does not tolerate slow disk (NAS) and large network latency.
Any slowness makes it lose a quorum slowing all of Kubernetes down
because everything depends on etcd performance. Round trip time (RTT)
must absolutely be less than 10ms but should usually be around 2ms for
peek efficiency.

Knowing this it is absolutely unthinkable to setup availability zones
that are more than 10ms RTT apart from each other, which includes
combining any on-prem cluster with any cloud service provider. Even
though this is well-documented, it is frequently discovered the hard way
by catastrophic cluster failure, which is bad. In short, even if it is
the third-zone don't even think about adding *any* zone that is more
than 10ms away. Usually this will mean keeping all your zones in the
same building or network, or, at worst, in two or three data centers
that are close to one another (network wise). 

Obviously this means that a true HA Kubernetes architecture (the kind
that would work even if an entire state where blown off the map) needs
to be composed of several clusters, perhaps with redundant deployments
of certain applications. Thankfully, most organizations and applications
do not have this requirement, but there are definitely some that do
(governments, financial institutions, etc.)

Related:

* Kubernetes Spanning Multiple Sites  
  <https://access.redhat.com/documentation/en-us/red_hat_openshift_container_storage/4.8/html/deploying_and_managing_openshift_container_storage_using_red_hat_openstack_platform/multicloud-object-gateway_osp>
* ETCD Performance Troubleshooting Guide  
  <https://access.redhat.com/articles/6271341>
* ETCD Backend Performance Requirements for OpenShift  
  <https://access.redhat.com/solutions/4770281>
* Using Fio to Tell Whether Your Storage is Fast Enough for Etcd
  <https://www.ibm.com/blogs/cloud-archive/2019/04/using-fio-to-tell-whether-your-storage-is-fast-enough-for-etcd/>
* Hardware recommendations \| etcd  
  <https://etcd.io/docs/v3.3/op-guide/hardware/>

Tags:

    #k8s #etcd #performance #availability #enterprise
