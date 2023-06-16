# When using minikube on LAN copying .kube/config enables any host

Just discovered that all the essential data for connecting to a minikube cluster is contained in the `.kube/config` file. This means copying that file *anywhere* on the same LAN will enable that system's `kubectl` to execute commands against that clusters API server transparently. This is a huge convenience when doing development on dev VMs or containers on that same network.
