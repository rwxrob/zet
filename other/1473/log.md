## Friday, September 17, 2021, 12:30:05PM EDT

Q: Do the control plane resource require a Kubernetes Node on can they
be just any machine?

All control plane components must be run on a Kubernetes Node (a machine
with `kublet`, etc. installed).

Q: What are the ports for `kube-apiserver`?

* 8080 for http
* 6443 for https

Q: How does `kube-apiserver` route requests?

`kubeadm` deploys every controller as a pod in `kube-system` namespace
and the `kube-apiserver` simply routes requests to *registered*
controllers/providers/pods. The `kube-apiserver` seems to be responsible
for registering everything with which it can broker communication.
It waits for an answer from the thing providing the response and then
sends it. It seems to handle time-outs as well and can be scaled
laterally by adding more instances of `kube-apiserver`.￼

> FunFact: You can interrupt (Control-C) `k delete ...` (and other long
> running stuff) rather than waiting around because the `kube-apiserver`
> has already initiated the work and all you are waiting for is the
> response from the controller.

Q: What do I have to do to make a 'Node'?

* Install container runtime (`docker`, `cri-o`, etc.)
* Install `kubelet`
* Install `kubeproxy`

Q: What should I do to practice this?

1. Install `minikube` locally and play with it
1. Build a virtual cluster using only VirtualBox (VMs)
1. Build a small on-prem hardware cluster
1. Build a small cloud cluster
1. Build a small hybrid cluster

Q: Can `kube-proxy` *write* to iptables config?

It definitely does attach rules to the "NAT pre-routing" hook in
iptables.

Q: Are all control plane resources in the same namespace?

By default, yes `kube-system` which you can see with `k get po -A`

Q: When Kubernetes control plane is installed, Core DNS is also?

Yes, by default (I think).

## Sunday, September 19, 2021, 12:07:45PM EDT

Q: What exactly are the resource types of control plan components?

`k get all -n kube-system` to see them all

## Friday, September 24, 2021, 12:05:03PM EDT

Q: How do I practice `kubeadm` commands?

## Saturday, September 25, 2021, 1:02:23PM EDT

Q: How do I simulate *real* K8S with just VirtualBox?

* Decided not to learn Vagrant or Ansible or Terraform (yet)
* Decided to attempt use of `vboxmanager` instead of GUI
* `kubectl` can install on anything, `kubeadm` only on Linux
* Thou shalt not install onto `mk ssh` minikube node (much magic)
* Don't forget to `sudo swapoff -a` before creating VMs

What are the steps to getting a learning cluster in VirtualBox?

*Assuming you only have 8 CPU and 16 GiB RAM.* All VMs should have at
least 2 CPU and 2 GiB RAM allocated.

1. Create a VM for the control plane components
1. Create a VM for a "master" Node
1. Create a VM for a "worker" Node

## Friday, October 1, 2021, 12:17:13PM EDT

* Decided *against* building physical cluster
* Planning on building a local virtual cluster on single computer
* Decided to pursue GCP for bigger "lab" projects
* Learning details of GCP K8S deployment more relevant than local VMs
* Reminded of personal priority to promote on-prem
* Learned about AWS Outposts (racks brought in-house, on-prem)

My path:

1. `kind` (k8s running in container engine)
1. `minikube` (k8s running in single virtual machine)
1. `virtualbox` + `kubeadm` + `clusterctl` (k8s in 3 virtual machines)
1. Google Cloud Platform (k8s running in 4+ virtual cloud machines)
1. On-Prem Bare Metal + `kubeadm`

## Friday, October 8, 2021, 12:19:33PM EDT

* KubeCon + CloudNativeCon is next week!
* New ClusterAPI and `clusterctl` released this week
* Decided to use `kind` instead of `minikube`

## Saturday, October 9, 2021, 12:19:13PM EDT

* Attempt to use standard OS images for nodes with `kind`

* TODO look into MaaS using Canonical offering

