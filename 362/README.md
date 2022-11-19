# VirtualBox is Best with Hyper-V On

Update: Latest version of VirtualBox has a critical bug with Hyper-V
that causes random CPU loop locks. Oracle has publicly announced no
planned support for Mac M1 and is internally getting off of it so they
can abandon it permanently. I will *never* use it again after the crap
it has put me through migrating off of it. VMware may be proprietary,
but it is rock solid, which is why it is the enterprise standard (and
VirtualBox is not).

While disabling the WSL2 feature in Windows I noticed that Hyper-V is
still on. I did some research and it turns out using VirtualBox *with*
Hyper-V enabled is still better than disabling it and forcing
"paravirtualization" instead.

* Use VirtualBox 6.0 and Hyper-V at the same time thanks to the Hyper-V API - Virtualization - Tutorials - InformatiWeb  
  <https://us.informatiweb.net/tutorials/it/virtualization/virtualbox-use-virtualbox-and-hyper-v-at-the-same-time.html>
