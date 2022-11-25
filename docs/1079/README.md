# Modern Approach to Workstation Configuration

The current infrastructure engineering job and my focus on preparing
people for such jobs me really rethinking about how modern
virtualization and containerization has radically changed the best
approach to getting a workstation setup and configured quickly, and
being able to reconfigure just as quickly when needed. The relevant
modern technologies include:

* VirtualBox/VMware
* QEMU/KVM 
* cloud-init
* Ansible
* Containers (Docker)
* Terraform
* Vagrant
* Chocolatey (Windows)
* Brew (Mac)

> 💭
> Let me say that we are automatically discounting any remote (usually
> web based) workstation solutions since they create a critical
> dependency on an Internet connection that not only consistently works,
> but has very low lag.  

Since you can create terminal workspaces in both virtual machines and
simple containers the first important question ...

## Virtual Machines or Containers?

If you are doing simple development, or even light-weight Kubernetes
testing you can get away with just having a container engine (like
Docker). But there's a catch. And container engine requires a virtual
machine in which to run. People don't realize this at first, but that is
exactly what Docker Desktop (or Rancher Desktop) installs. Since Docker
Desktop is 100% proprietary (with some companies prohibiting it) and
Rancher Desktop is still very buggy 1.0 software this leaves no other
possibility for many people.

## One Possible Best Way

The best way to get work done in 2022 seems to be install a headless
VirtualBox VM running your preferred Linux server image and ssh into it
providing a local "cloud"-like server on your desktop. Then, install
your preferred container engine without problem since, after all, these
things love a good Linux server to run. You can even experiment with
*different* container engine and Linux distro combinations, which you
cannot do with just installing stuff into the host OS. Having a VM
approach, therefore, seems like a no-brainer for everyone in tech.

1. Install iTerm2 and Brew (Mac)
1. Install Windows Terminal, Git-Bash, Chocolatey (Windows)
1. Install VirtualBox
1. Install a Ubuntu Server VM (ISO) with OpenSSH and Docker
1. Create a `dot` repo with `install` directory for custom installs

