# Reasons to Stick with Boring OS for Kubernetes

Been giving a lot of thought to what to put on all the old hardware I
have laying around. None of it is very big. I thought of ProxMox, but my
Minis don't support KVM (type-1 hardware virtualization). So I started
looking at what Kubernetes-aware OSes to try. I love RancherOS (which is
now k3os).

Then, after reading the argument for "boring" OSes related to getting
people to hire to maintain it, I got to thinking about all the specific
stuff in the k8s node setup script we maintain at work in order to make
sure the Nvidia drivers are correct and more. That's when I realized 
these specialty OSes probably don't allow any of that. I
would have to do when provisioning hardware in the first place. 

Talos is one of the OSes I was really encouraged to consider. But it is
a *very* locked down OS that doesn't allow anything but reads. The
argument for it is that "it's just an IP address at the end of the day".
But this is just wrong. Perhaps in some boring, homogeneous clouds this
is true, but it is so *not* true for most HPC clouds with all sorts of
different GPUs and configurations. You cannot escape infrastructure
management in those cases.

My conclusion is that we are at least three years from any solid
Kubernetes OS that can take into account the infinitely different bare
metal device configurations, in fact, looking into all of this has
really put the kibosh on my dreams of a fully Kubernetes managed IT
environment, at least one where all I have to do is load a RAM-disk
image into a machine and open up some dashboard or command-line to
provision the hardware (as ProxMox promises).

As long as this reality exists, things like OpenStack will be the
unfortunate reality for people like me with *really* old hardware, even
Raspberry Pis.

Tags:

    #baremetal #k8s
