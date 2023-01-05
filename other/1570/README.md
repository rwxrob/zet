# cloud-init is Mandatory Learning

I know I'm late to the party on this, but after a read of the
documentation for cloud-init and using it with VMware to instantiate a
virtual machine it really should be considered mandatory learning. This
is how all virtual machines are deployed to *every* cloud provider and
virtualization platform, even VirtualBox is supported.

At this point I'm a little disappointed that I spent any time on Vagrant
at all. I am glad that I understand it now and have used it, but it is
so overwhelmingly clear that writing simple scripts that deploy locally
using cloud-init are far more sustainable and produce more valuable
learning and skills overall because everything directly translates to
provisioning virtual machines in *any* cloud environment, vendor or
on-prem.

Just the ability to specify which packages to install and set your own
follow up provisioning scripts makes cloud-init in a class by itself.
All the stuff that I once did for a "workspace container" is relevant,
but this is just so much better because it is a *real* machine with
volumes that I can mount and test and fill. Such cannot be done with
containers.

Related:

* https://cloud-images.ubuntu.com/releases
