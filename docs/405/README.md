# Home OpenLDAP/OIDC Provider

One of the most critical components of any IT infrastructure is a method of authentication and authorization for different applications. OpenLDAP is a standard for authentication used for decades. OpenID, or OIDC, is a method of authorization used prevalently for about a decade at this point. Understanding how to set both of them up and use them to authenticate an application consistently is a core skill for any infrastructure engineer. Unfortunately, I the last time I did OpenLDAP was in the 90s way before OIDC even though I've written the `klogin` that uses OIDC at work currently and my own `auth-go` for doing three-legged OAuth sessions. But I really need to go through the entire process of setting both of them up on my home lab, no Terraform, no Ansible, just a VM running both that I can migrate later.

There are a number of option here:

1. Clean install into a VM or physical machine
1. Create a container on VM or physical with container engine
1. Create a Kubernetes app to contain it all

I'm prone to do #2 because Kubernetes makes heavy use of OIDC itself, a sort of chicken-and-the-egg syndrome. A VM is nice and all, but if I want to provide any sort of redundancy I'd be looking at lots of extra work.

I'm going to use a RedHat variant (Rocky or Alma) since it is --- by far --- the most prevalent enterprise Linux distribution (despite my feelings about RedHat).

I'm going to install OpenLDAP into three different containers on three different VMs to simulate redundancy. I'm not going to put OpenLDAP itself into Kubernetes because I feel like that adds too many unnecessary moving parts and points of failure for what is going to be one of the most intensely used infrastructure services. Some might feel that is a reason to put it into Kubernetes, but I'm just not sold on the idea. It's like DNS. Would I put DNS *inside* of Kubernetes? No way.

I'm going to use Podman for the container engine on the Rocky Linux distro because it is common and I need some exposure to Podman given its enterprise prevalence. I don't particularly like Podman, but it doesn't matter, that is what is used.

I'm going to use Hashicorp's Vault (written in Go) as opposed to Keycloak (written in ancient Java) since that is the direction of our company eventually even though we are hopelessly dependent on Keycloak for now. Still don't know if will put into K8S or run stand-alone.

* Install and Configure Open LDAP  
  https://www.tutorialspoint.com/linux_admin/install_and_configure_open_ldap.htm
* Implementing LDAP authentication for Kubernetes \| by Daniel Weibel \| ITNEXT  
  https://itnext.io/implementing-ldap-authentication-for-kubernetes-732178ec2155?gi=a1e2c318d604
* Install Vault  
  https://www.vaultproject.io/docs/install
* OpenLDAP in docker container? : devops  
  https://www.reddit.com/r/devops/comments/9dtnn2/openldap_in_docker_container/
* Configure OpenLDAP on Rocky Linux 8 \[Step-by-Step\] \| GoLinuxCloud  
  https://www.golinuxcloud.com/install-configure-openldap-rocky-linux-8/
* Authenticate to Kubernetes using Hashicorp Vault -- /var/log/tmaurice  
  https://blog.thomas.maurice.fr/posts/authenticate-with-kubernetes-using-vault/
* How do I setup my own LDAP server? -- Clambaronline.com  
  <https://www.clambaronline.com/how-do-i-setup-my-own-ldap-server/>
