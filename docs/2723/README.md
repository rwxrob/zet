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
sudo kubeadm init \
  --control-plane-endpoint 192.168.1.200 \
  --pod-network-cidr 10.98.0.0/12 \
  --upload-certs
```

Copy the join command in the output to save time.

```
sudo kubeadm join 192.168.1.200:6443 --token lnsp3y.roc52nu49xwswvqq \
        --discovery-token-ca-cert-hash \
        sha256:b462f7e4b85217fc8da0b4b7de831912ec0ff440cc69edf8e50886057c1e34c6 \
        --certificate-key \ 5034f880c08e58644ec9c31302d7213b789a56d0a2b19700b88981a454b13fc3 \
        --control-plane
```

(Don't need both, second doesn't have `--control-plane` and `--certificate-key`, otherwise identical.)

Note that CoreDNS will be broken until the CNI is setup

```
kubectl apply -f https://raw.githubusercontent.com/projectcalico/calico/v3.25.0/manifests/calico.yaml
```

Or `install-calico` instead.

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
* <https://github.com/kube-vip/kube-vip/issues/684>
* Because of 1.29 k8s changes, `super-admin.yaml` is needed only on first control plane `kubeadm` call, after that leave as `admin.yaml` in `kube-vip.yaml`
* Secondary control planes for 1.29 need `/etc/kubernetes/pki` copied over

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
