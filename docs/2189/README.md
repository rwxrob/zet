# Minikube uses files instead of inline certs if .minikube/certs

It appears that the `minikube` command will create a stand-alone `.kube/config` file that can be shared on any system to work with accessing the k8s API for that minikube from anywhere on the same subnet. However, when providing your own CA (or interm CA) in `~/.minikube/certs` before doing a `minikube start` the resulting `.kube/config` file has dependencies on file paths within the *local* `.minikube` directory that must also travel to the any hosts on the same subnet that want to issue `kubectl` commands (and the like) using that information. This just adds a few steps to setup in such cases.