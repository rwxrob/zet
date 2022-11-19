# No `kubeadm`? You're Probably Doing it Wrong

TL;DR: Use `kubeadm` to make your *real* cluster

I've come to realize that using `kubeadm` to bootstrap Kubernetes
clusters is truly the official way to create an on-prem production
cluster, period. There are many reasons people do not, including vendors
that supply their own, but one of the reasons (we just want to do our
own thing) might be a bad one. Upgrading between versions when *not*
using `kubeadm` is a lot more work. And even keeping things like `etcd`
out of the `kubeadm` administration scope can cause outages just for
having expired certificates (as it did to us).
