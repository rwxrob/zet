# Conventional `kubeadm init` Command for Vagrant

I've hit an unusual problem when using Calico on Kubernetes deployed to
local Vagrant virtual machines provisioned with `kubeadm` directly. It
seems the problem is related to Vagrant's requirement for `eth0` as the
"management interface" requiring the creation of an additional `eth1`
with the `private_network` Vagrantfile directive. This change to the
default forces certain optional arguments to be required. To put it in
the words of @proportionate, "Calico wants to be on the default route
interface, which makes Vagrant kinda whack." (Also thanks to @lbgdn for
spending hours helping debug the issue.)

```
kubeadm init \
  --apiserver-advertise-address 10.0.0.2 \
  --pod-network-cidr 192.168.0.0/16
```

The `--apiserver-advertise-address` is the IP address that the API
server will advertise it's listening on. This will be "external" and
listening on 6443 (which you can test with `telnet` or `nc`). If not set
the default network interface will be used, but this is a huge problem
when working with Vagrant where `eth0` might be a 10.0.2 address and you
have added a second `eth1` interface for the `private_network` to get
stuff to talk to each other. Without adding this, your setup will
default to an interface that isn't connected to anything.

Even though the `--pod-network-cidr 192.168.0.0/16` seems unnecessary, we
had been wrestling with for hours related to very strange errors related
to being unable to contact the 10.96 services, even though those default
service IPs seem to have nothing at all to do with the rest. Moral of
the story: *always* add a `--pod-network-cidr` to *any* `kubeadm init`
attempt that involves Vagrant will always need it.

* kubeadm init \| Kubernetes  
  <https://kubernetes.io/docs/reference/setup-tools/kubeadm/kubeadm-init/>
