# Kubernetes 1.22+ Supports Kubelet Swap Memory

That's right, remove that `swapoff` step from your machine preparation.
You don't need it any longer.

While it might not be good to enable swap on virtual machines running on
SSD (as many host providers have) it is nice to know that the Kubernetes
finally woke the fuck up and realized that swap memory still has many
modern advantages, not the least of which is preventing catastrophic
crashes and hard system freezes.

Related:

* <https://kubernetes.io/docs/concepts/architecture/nodes>

Tags:

    #k8s #memory #constraints
