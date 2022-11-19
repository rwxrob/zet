# Linux on VirtualBox, Best First Linux Experience

***UPDATE: VirtualBox does *not* work on M1 Macs.***

2021 Beginner Boost had me experimenting with Docker Desktop as a
person's first experience with Linux, but events of this year have
convinced me to go back to VirtualBox for 2022.

**VirtualBox just works, everywhere.** It is easy to install on anything
and just works out of the box (pun intended).

**VirtualBox allows for safe experimentation.** Want to try 10 different
Linux distros in a day? VirtualBox is the only way to do that without
the pain and suffering of re-installing everything on hardware. This is
also a great way to sample changes to a distro to see if you want to
upgrade (which I wish I had done with PopOS, which I now very much
hate).

**VirtualBox machines have persistent state.** This is a big deal for
beginners. The ephemeral nature of containers is nice and all, but
horrible for beginners who don't want to have to redo their work all the
time and might accidentally reset. This is virtually impossible with a
virtual machine. Yet, if a beginner does want to start with a Linux
machine from scratch and build it up they absolutely can with a VM using
whatever distro they prefer.

**VirtualBox machine images are real.** The machine might be virtual,
but the OS distro and all its files are real, no missing man pages,
minimized packages, and missing tools one might expect. But, if you want
minimal you still have the option of creating a minimal VM.

**VirtualBox has been the primary driver for Vagrant for years.** Just a
single look at the Vagrant cloud listings will show the overwhelming
dominance of VirtualBox driven Vagrantfiles. My new-found affection
(after a rough early relationship) for Vagrant has driven VirtualBox
further into the definitely-learn-this category (along with keeping up
one's Ruby skills). The ultra-simplified Vagrant "experimental" `disk`
directive only works with VirtualBox, for example.

**VirtualBox includes a command-line and light-weight images.**
I had not fully realized that VirtualBox can be used to bring up
ultra-light images that don't even have a graphic user interface. This
is what Vagrant does. When using Vagrant updating your `~/.ssh/config`
is as easy as `vagrant ssh-config` and you have instant ssh access to
your virtual machines just like they were on a local private network.

**Docker Desktop is proprietary software and no longer free for business
use.** Even though this does not affect beginners, students, and those
with small businesses, it does affect anyone working for a bigger
company, eventually. Besides, this is a proprietary cash grab from a
company that has already proven to fuck-over Kubernetes rather than to
the right thing. So I have no intention of supporting Docker as a
company any longer. I'm actively moving my container images off of
Docker and onto GitHub or other locations and will be encouraging others
to learn how to do the same.

**Linux virtual machines can run Docker.** In order to get around all
the shit with Docker Desktop you can just run Docker within a VM. This
allows one to get all the benefit and get used to installing `docker-ce`
on anything else they might wish later.

**VirtualBox is a better driver for Minikube than Docker.** Even though
Minikube will now default to Docker if detected (creating
pseudo-machines that are running containers instead of virtual
machines) it makes little sense to do so. Kind does Docker containers
for such things much better (and was likely the inspiration behind the
Minikube change) and Minikube benefits from actually using `kubeadm` to
create it's nodes meaning that when using VirtualBox you get the
protections of a normal machine with regard to volumes and such. It also
means that you can use Minikube to experiment with NFS and additional
storage classes because you can use VirtualBox to provision additional
volumes and connect them up with Minikube nodes. That's not something
you can do with Kind. This is nice because it allows testing the
creation of StorageClass drivers and other such things that need a
virtual machine that is more real than a containerized one.

    #virtualbox #virt #docker #vm #education #edtech
