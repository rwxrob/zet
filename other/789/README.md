# Control-Plane Components are Executables in Pods

Today I happened upon a revelation that was quite accidental but really
helped me understand the present and past of the components of the
Kubernetes control plane. Here's what Kelsey Hightower would have you do
"the hard way" to get your control plane components installed:

```bash
wget -q --show-progress --https-only --timestamping \
  "https://storage.googleapis.com/kubernetes-release/release/v1.21.0/bin/linux/amd64/kube-apiserver" \
  "https://storage.googleapis.com/kubernetes-release/release/v1.21.0/bin/linux/amd64/kube-controller-manager" \
  "https://storage.googleapis.com/kubernetes-release/release/v1.21.0/bin/linux/amd64/kube-scheduler" \
  "https://storage.googleapis.com/kubernetes-release/release/v1.21.0/bin/linux/amd64/kubectl"

chmod +x kube-apiserver kube-controller-manager kube-scheduler kubectl
sudo mv kube-apiserver kube-controller-manager kube-scheduler kubectl /usr/local/bin/
```

If that doesn't make your gasp in horror I really don't know what to
say. 

Consider first that he's not using `curl` (that's a no brainer). Then
consider that all of this stuff now has standard images that are pulled
with `kubeadm config pull images`, and that there is a perfectly good
`apt` package archive for all of this stuff as well even if it were not
available as images.

The fact that this anti-pattern was ever recommended reveals something, I
think, about the history of Kubernetes. I don't know, but I can imagine
that once upon a time people actually did install the very binaries that
made up the "control plane components" that are diagrammed so well on
the kubernetes.io site. In fact, perhaps this is why the diagrams are so
unclear as what the things in the diagram actually are. I assume it is
still entirely possible to use the binaries directly, or the versions
contained in the containers, which, I think, become Pods.

This has made for some *very* confusing realities which have beginners
everywhere really scratching their heads.

I'm sure I have lots of this completely wrong. I'm still learning it.
But I can state without question that *no one* should ever recommend
this tutorial to anyone. At best, it was once upon a time relevant.
These days it will just confuse the hell out of everyone when they then
read the official documents.

Related:

* <https://github.com/kelseyhightower/kubernetes-the-hard-way/blob/master/docs/08-bootstrapping-kubernetes-controllers.md>

Tags:

    #k8s #cloud #learning #rants
