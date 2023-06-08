# Preferred multi-cluster developer workflow

Here are some thoughts about how to best manage development for multiple clusters from a single workstation with the following considerations:

* Multi-cluster is becoming the preferred enterprise K8S architecture.
* Kubernetes development requires `kubectl` be within two versions of server.
* Theoretically developer could be required to use different `kubectl` binaries.
* `~/.kube/config` is the standard default config file location.
* Kube config can contain multiple contexts with different clusters.
* Format of kube config not specified.
* Kube config file changes overridden by most `kubectl` commands that use it.
* `KUBECONFIG` environment variable defines location for `kubectl`.
* `kubectl` does not take argument to define Kube config location.
* `kubectl proxy` dashboard use prompt for token or path to Kube config.
* Theoretically Kube config schemas could change between kubectl versions.
* Enterprise OIDC Connect Kubernetes authentication is common practice.
* OIDC Connect requires creation of a token from OIDC provider.

Suggested steps for working with a specific cluster:

1. Install `kubectl` version that matches target cluster.
1. Generate and download a Kube config file to common location (with others for other clusters).
1. Promote use of `KUBECONFIG=~/... kubectl`

Related:

* <https://goteleport.com/kubernetes-access/>
* <https://github.com/vmware-archive/gangway>
