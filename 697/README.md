# Home Lab ("on prem") IT Architecture for Learning

Here's a summary of the lab I'm slowly building at home to model those I
use in production on the job. I still feel it is well worth the cost and
effort to do this at home "on prem" over using a cloud provider because
the entire point is being able to be productive on-prem or in the cloud.
Using only a cloud service provider robs me of the critical learning
opportunities setting something up that is done "for me" by those
providers (like Kubernetes Ingress, CNI, IAM, DNS, etc.)

Keep in mind the goals of this lab are not to keep things the same, but
to have a sample of the most likely tech to encounter in the enterprise,
(for example, both RedHat and Ubuntu servers).

Here are the stand-alone components:

* NTP
* CoreDNS
* OpenLDAP IAM
* Keycloak OIDC
* Harbor Container Registry
* Kubernetes Container Orchestration
* Sidero K8S on Metal (Raspberry Pis, etc.)
* Podman and Containerd Container Engines
* Rocky and Ubuntu Linux Servers
* Synology NFS
* UPS
* TFTP/Boot
* Gitea
* Proxmox Pool (but not for Kubernetes)

Kubernetes with HA will have its own batteries-not-included to setup as
well (which is why you want a home lab and not some cloud provider that
does this all for you robbing you of the learning opportunity):

* Calico CNI
* Istio Ingress/Mesh
* Vault
* Tekton
* NFS Storage Class
* User ServiceAccounts

A year ago I couldn't even tell you what all that architecture was about
and why it was needed. Unfortunately, I can tell you why it is needed
now, but still struggle to keep my management skills of all of it up to
snuff.

I'll be doing most everything from hardware and "netbooting" but I will
do a Proxmox collection of VMs for some quick cloud applications as
well, even though most of my work will be involving in-cluster
Kubernetes application builds.

    #learning #k8s #boost
