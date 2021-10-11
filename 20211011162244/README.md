# Amazon Dropped Xen for KVM in 2019

All I needed to know about the future of Linux virtualization and
hypervisors comes from the announcement in 2019 that Amazon built
"Nitro" on KVM and dropped Xen. KVM requires hardware support for
virtualization (type-1 hypervisor). It *must* have it. Xen is more
flexible and does not (type-1 or 2 hypervisor). These days, ff you need
emulation you are doing something wrong or don't care about performance.
As for me, I'd rather never risk it. I'm *only* using KVM for everything
as a method of weeding out my old hardware from the new (which is still
several years old).

I learned this while looking into the amazing ProxMox project, which
only used KVM and might not work on my slew of old Mac Minis if they
don't have hardware support.

Tags

    #hypervisor #virt #xen #kvm #amazon
