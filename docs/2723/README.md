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

* Rerun `install-kubeadm` (for swap, `socat`, and `ip_forward`)

## Control planes only

* Duplicate the `k8s-node` control planes (`k8s-control-{1,2,3}`)
* `install-kubevip`

```
sudo kubeadm join 192.168.1.200:6443 --token oduj4q.6siu25l52735qp4j \
        --discovery-token-ca-cert-hash sha256:fa121b53ec5fc9e21ec3abee18e6375399ca93bfbaf91f3f5464840cc8f962e6 \
        --control-plane
```

Related:

* Install KubeVIP: <https://kube-vip.io/docs/installation/static/>

## Required steps when cloning from `k8s-node` image

* Remove duplicate host keys: `sudo rm /etc/ssh/ssh_host*`
* Recreate host keys: `sudo ssh-keygen -A`
* `sudo systemctl restart ssh`
* Change the host name

## Troubleshooting

* "you should never need a `kubeadm reset`
* If you do remember to regenerate the `kube-vip.yaml`

## Stuff to learn

* `cloud-init` (again, and for multiple different OSes)
* `podman` (more)
* `runc`
* `crictl`
* `ctr`
* ssh changing to socket in Ubuntu
* read and understand `kubeadm` phases

## Related:

* <https://discourse.ubuntu.com/t/sshd-now-uses-socket-based-activation-ubuntu-22-10-and-later/30189>
* <https://computingforgeeks.com/install-kubernetes-cluster-ubuntu-jammy/?expand_article=1>
