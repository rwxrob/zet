# Apparently No Way to Determine CNI of Cluster

While trying to setup a CNI in my Vagrant local cluster built with
`kubeadm` I realized there is no `kubectl` you can do to determine it.
You have to look around at the host environment or infer it from the
running Pods. All I wanted to do was look at an existing cluster to tell
what it is using. Seems like a simple enough thing to want to figure
out.

The best I could figure out (with the help of friends) is to look in
`/etc/cni/net.d` and use the process of elimination. For example, after
having installed Calico I have the following:

```
$ ls /etc/cni/net.d
10-calico.conflist  calico-kubeconfig
```
