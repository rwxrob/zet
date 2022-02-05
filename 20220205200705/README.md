# Choose the Right Desktop Tools for *Real* Jobs

Here's my latest thinking about the best tools for the best
infrastructure engineering and cloud-native applications development
jobs. Keep in mind these conclusions take *everyone* into account, not
just the edge cases.

Consider the following realities:

* Most tech jobs are not for an IT company
* Most companies require Mac or Windows desktop hosts
* Linux desktop is not even an option for most tech work
* Containers require a Linux kernel
* Mac and Windows require a VM to run containers
* Most tech workers only have one main computer
* Most jobs don't allow work on personal computers
* Tech work is largely remote these days
* Tech work depends on productivity without Internet

So, tech workers need a VM solution that runs on Windows or Mac.

* Docker and Rancher Desktop provided a tiny Linux VM
* Docker Desktop works with Cisco VPN, Rancher does not
* Docker Desktop is proprietary and soon banned at most companies
* Rancher Desktop is less than alpha software with tons of bugs
* You cannot access the Docker/Rancher VM directly
* VMware and VirtualBox provide VMs for Windows Mac

Why not WSL2?

* WSL2 is a VM with tight Windows integration
* WSL2 lacks `systemctl` and Cisco VPN support
* WSL2 cannot snap-shot like VMware or VirtualBox
* WSL2 is a great PowerShell replacement at best
* WSL2 has problems working with Docker
* WSL2 has only limited graphic support

But which of the two is a better pick for most tech jobs?

* VMware started the consumer virtualization market
* VMware Workstation Pro is preferred by professionals
* VMware Workstation Pro is expensive but has "free trial"
* VWware Workstation Player is free but limited
* VMware Fusion is run-Windows-on Mac VM
* VirtualBox was bought by Oracle
* VirtualBox has historically conflicted with WSL2 VM
* VirtualBox is late to receive updates
* VirtualBox has conflicts with Rancher Desktop
* VirtualBox does not support Mac M1 architecture

What about graphic application dependencies?

* Most infrastructure engineering jobs have let GUI deps
* VirtualBox gets screen size wrong
* VMware and VirtualBox support full graphics applications
* VMware had proven track record with GPU pass-through
* VMware and VirtualBox have command line interfaces
* WSL2 has shoddy graphic support but does integrate with Windows

VMware Workstation Pro is the best choice for more tech work
and should be an essential tool that every tech professional saves up to
buy eventually. 

VirtualBox is good for those just starting out who don't yet have the
money.

Can't I do everything in a workspace container instead?

* For *most* development tasks the answer is "yes"
* Containers limit tasks for infrastructure engineering
* Containers share the host operating system and devices
* You cannot mount different block devices for each container
* Containers have really shoddy support for `systemctl`
* Kubernetes CNI and CSI work requires a VM

Conclusions:

* Local VMs are the closest approximation to IT systems
* Buy and learn VMware Workstation Pro first if you can
* Explore several different OSes in VMware to learn
* Maintain a primary workstation VM (GUI or no-GUI)
* Install Windows Terminal or iTerm2 just to connect
* Consider activating WSL2 just to get bash instead of posh
* Setup ssh from Windows or Mac shell (any shell is fine)
* Install and run (Docker) containers in a true Linux VM
* Install and run Kubernetes on a small local cloud of VMs
* Use `fluff` to simplify working with clouds of desktop VMs

And related to the Beginner Boost here's the steps to get started
(revised from 2021):

1. Install Windows Terminal or iTerm2
1. Install VMware Workstation/Fusion Pro or VirtualBox
1. Download `fluff` and `fluff up` a local cloud of VMs
1. Use default password to `ssh` into local cloud VM

As for the Boost projects, challenges, and other exercises we'll be
creating them as docker containers, VMs, `fluff` clouds, and the combination of them.
