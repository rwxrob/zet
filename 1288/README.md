# Always Coordinate etcd Upgrades with Kubernetes

When running an "external" etcd cluster from Kubernetes every Kubernetes
upgrade needs to be grouped with an etcd upgrade as well (if required).
In other words, etcd and k8s are not on separate upgrade paths in these
cases. This might now be obvious to people who are used to running etcd
in a pod within Kubernetes as is the default when setting up with
kubeadm. It also means that the entire Kubernetes cluster must be taken
down, or that *new* etcd nodes need to be independently setup before the
Kubernetes upgrade can be pointed to them.

