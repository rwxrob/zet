# Kubernetes Components are Mostly Executables in Pods

One of the most confusing things I encountered has been things like the
direct references to `kube-proxy` and `kubelete` compiled Go binaries in
Kelsey Hightower's "Hard Way" tutorial. It wasn't until I read that
`kube-proxy` is actually deployed as a DaemonSet by `kubeadm` even
though it could be (technically) deployed by installing and running the
`kube-proxy` command all by itself that I realized what was going on and
why so many people are so fucking confused.

Pretty much every major component *is* a Go program that has been
wrapped into a Pod. This goes for everything in the control-plane
except `etcd` (which you might not want to deploy on the same machine as
the rest of your control-plane anyway). This is why all the diagrams
showing these components are always so non-precise. There's no precise
indication what a thing actually is. This is why when I do a diagram of
everything every component in the diagram will have a key and a specific
type:

* Executable
* Process
* Pod
* DaemonSet
* etc.

> 💡
> This reminds me that I really need to just fucking read all the
> Kubernetes code, or at least scan it. There's no way to know what is
> actually going on without having to sift through someone else's lame
> abstractions and explanation and going directly to the code. Learn Go
> people, learn Go.

Related:

* Options for Highly Available topology | Kubernetes  
  <https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/ha-topology/>

Tags:

    #k8s #learning #concepts #tips
