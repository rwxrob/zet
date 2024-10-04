# Notes on installing Kubernetes into home lab

* Install Proxmox
* Create an Ubuntu 24.04 template
* Clone the template into `k8s-node`
* Install `avahi-daemon`
* Clone `github.com/rwxrob/dot`
* Take a VM snapshot
* `install-kubectl`
* `install-kubeadm`
* `install-kubelet`
* `install-containerd`
    * `containerd`
    * `runc`
    * plugins
* `jq` (already installed)
* `yq` (from `apt`)

## Stuff to learn

* `podman` (more)
* `runc`
* `crictl`
* `ctr`
