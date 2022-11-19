# TIL `kube-public` is Created by `kubeadm`

Doing an audit of everything with `nstype=system` in our production
cluster and a bit of research revealed that `kube-public` namespace is a
standard namespace used by `kubeadm` during creation. I appears that
eventually it might go away, but the latest `minikube` still has it.

Tags:

    #k8s #kubeadm
