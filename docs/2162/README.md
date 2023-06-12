# Preferred multi-cluster Kubernetes developer workflows

What is the best Kubernetes developer workflow to promote for an enterprise with multiple, disparate Kubernetes clusters with some in the cloud, some on-prem, some very old versions and some the very latest?

Here are some facts and considerations to help make the best workflow suggetion:

* Multi-cluster is becoming the preferred enterprise K8S architecture.
* Kubernetes development requires `kubectl` be within two versions of server.
* Developers may be forced to use different `kubectl` binaries based on cluster versions.
* `~/.kube/config` is the standard default config file location.
* Kube config may contain multiple contexts with different clusters.
* Format of kube config is not specified.
* Kube config file changes overridden by most `kubectl` commands that use it.
* `KUBECONFIG` environment variable defines location for `kubectl`.
* `kubectl` does not take argument to define Kube config location.
* `kubectl proxy` dashboard use prompt for token or path to Kube config.
* Theoretically Kube config schemas could change between kubectl versions.
* Enterprise OIDC Connect Kubernetes authentication is common practice.
* OIDC Connect requires creation of a token from OIDC provider.
* For for `grant_type=password` is *only* way to integrate non-web based username/password.
* LDAP authentication backed OIDC providers may require `grant_type=password`.
* Flow for `grant_type=password` is deprecated and not in OAuth2.
* Trusting binary to authenticate requires vetting and reviewing binary source.
* Trusting binary in trusted environment where enterprise controls binary is fine.
* Openshift login requires copying and pasting `oc*` command from login page.
* Google cloud requires pasting token from URL after opening (most common).

Suggested steps for working with a specific cluster:

1. Install `kubectl` version that matches target cluster.
1. Generate and download a Kube config file to common location (with others for other clusters).
1. Promote use of `KUBECONFIG=~/... kubectl`

Related:

* <https://goteleport.com/kubernetes-access/>
* <https://github.com/vmware-archive/gangway>
