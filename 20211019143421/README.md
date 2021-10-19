# Staged Approach to Understand How Kubernetes Works

A stage approach seems to be materializing from my own struggles to
learn the entirety of Kubernetes. I'll be updating this zettel as I go.

Before you begin any of this you must have proficiency in the following:

* Linux Bash Command Line
* Git and GitHub for Source Management
* CommonMark Markdown
* Bash Scripting
* JSON / YAML
* Go Template Language
* Web Essentials (HTML, CSS, Plain JavaScript, DOM, HTTP)
* Networking and Network Troubleshooting
* Using and Creating Containers with `docker` and `Dockerfile`
* (There is no need to learn Docker compose.)

Here's a quick overview in a prioritized order:

1.  Get familiar with Kubernetes component architecture and communication
2.  Get familiar with all standard Kubernetes resources
3.  Use kind to deploy a simple app
4.  Use minikube to deploy a simple app with an exposed service
5.  Use kubeadm init to deploy cluster in VirtualBox and app
6.  Use kubeadm init to deploy cluster in Docker and app
7.  Use kubeadm init phase to deploy cluster one phase at a time and app
8.  Deploy single-node cluster in phases “the hard way” (no kubeadm)
9.  Use kubeadm to deploy multi-node cluster using cloud provider
10. Deploy multi-node cluster in cloud without kubeadm
11. Use kubeadm to deploy multi-node cluster on-prem on own hardware
12. Deploy multi-node cluster on-prem on own hardware without kubeadm

When you finish all of these 12-steps you'll easily pass any
certification exam and would be immediately able to deploy any
Kubernetes flavor for any potential customer or organization.

Keep in mind this does *not* include all of the extra stuff anyone needs
to understand and deploy that comes along with Kubernetes (Istio, Helm,
ElasticSearch, Prometheus, Thanos, Sidero, Calico, Nginx, OpenSSL
Certificates, etc.)

Here's a more detailed version:

1. Study the components of a Kubernetes worker and control-plane node.
   Create a diagram from scratch showing your own understanding of them
   and how they connect logically. Be prepared to explain the function
   of each, whether it is optional, and how it is implemented and
   deployed.
1. TODO 

Tags:

    #learning #k8s #planning
