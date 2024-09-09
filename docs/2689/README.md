# Harbor at home (lab)

Harbor container registry is one of the core systems I need to support and install. I need to get good at bringing up and tearing down the essential Kubernetes infrastructure in my home lab to try different install procedures and automations that integrate `kustomize` and Ansible primarily driven by GitOps.

I wonder standing up and tearing down a full k8s cluster built on VMs with Ansible would be worth looking into. It would have to have everything, Calico CNI, MetalLB, KubeVIP and a reasonable network file system.
