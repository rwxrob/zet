# Always Have Odd Number of Control Plane Nodes

Even though the Kubernetes documents say that you need a "minimum of
two" control plane nodes for high-availability, it is always better to
have three and if you have more to make sure you have an odd number.
It's a little hard to get my head around, but the election of the
authoritative state once everything comes back online needs the odd
number to break the tie that would otherwise occur if there were an even
number. It's one of those situations where "it works until it doesn't,
and then it *really* doesn't". Our ES SME has explained this situation
pretty well.

The good news is that almost all HA design architectures depend on the
same pattern and algorithm even if they are implemented in different
ways. This is one of those examples where reading *Enterprise Business
Patterns* is as important (if not more so) than things like data
structures and algorithms when dealing in the operations space. Both are
certainly important and provide a good foundation for thinking in
general, as in cognitive architectural design patterns without any
specific implementation in mind (even though `etcd`, `control-plane`,
and `eck` all use slightly different algorithms).

Related:

* K8s Control Plane Fault-tolerance \| Minimum nodes and Leader Election
  <https://stackoverflow.com/questions/68178282/k8s-control-plane-fault-tolerance-minimum-nodes-and-leader-election>
