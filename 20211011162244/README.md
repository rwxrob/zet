# Amazon Dropped XEN for "Home Brewed" KVM in 2019

All I needed to know about the future of Linux virtualization and
hypervisors comes from the announcement in 2019 that Amazon built
"Nitro" on KVM and dropped Xen. Xen is more flexible and does not
(type-1 or 2 hypervisor). I'm *only* using KVM for everything.

I learned this while looking into the amazing ProxMox project, which
only used KVM and might not work on my slew of old Mac Minis if they
don't have hardware support.

Related:

* AWS adopts home-brewed KVM as new hypervisor • The Register  
  <https://www.theregister.com/2017/11/07/aws_writes_new_kvm_based_hypervisor_to_make_its_cloud_go_faster/>
* AWS announced a move from Xen towards KVM. So what is KVM?  
  <https://www.freecodecamp.org/news/aws-just-announced-a-move-from-xen-towards-kvm-so-what-is-kvm/>

Tags

    #hypervisor #virt #xen #kvm #amazon
