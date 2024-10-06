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
    * `containerd.service`
    * `runc`
    * `/etc/containerd/config.toml`
    * `/opt/cli/bin` (plugins)
* `jq` (already installed)
* `yq` (from `apt`)

(forgot to do these before templating)

* Disable swap
    * `sudo swapoff -a`
    * `sudo perl -p -i -e  's,^/swap,#/swap,' /etc/fstab`
    * reboot
    * `sudo swapon --show`
* `sudo apt install socat`

## Control planes only

* Duplicate the `k8s-node` control planes (`k8s-control-{1,2,3}`)
* `install-kubevip`

Related:

* Install KubeVIP: <https://kube-vip.io/docs/installation/static/>

## Required steps when cloning from `k8s-node` image

* Remove duplicate host keys: `sudo rm /etc/ssh/ssh_host*`
* Recreate host keys: `sudo ssh-keygen -A`
* `sudo systemctl restart ssh`
* Change the host name

## Stuff to learn

* `cloud-init` (again, and for multiple different OSes)
* `podman` (more)
* `runc`
* `crictl`
* `ctr`
* ssh changing to socket in Ubuntu

## Related:

* <https://discourse.ubuntu.com/t/sshd-now-uses-socket-based-activation-ubuntu-22-10-and-later/30189>
