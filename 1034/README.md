# Setup KVM Virtualisation

* Bionic (18+) add to the `libvirt` instead of `libvirtd` group

* VMX: Intel
* SVM: AMD

> The CPU flag for Intel Hardware Virtualization is VMX. VT-x is Intel
> Hardware Virtualization which means they are exactly the same. ... The
> CPU flag for VT-x capability is "vmx"; in Linux, this can be checked
> via /proc/cpuinfo ... The CPU flag for AMD-V is "svm" in Linux via
> /proc/cpuinfo.[19] Instructions in AMD-V include VMRUN, VMLOAD, VMSAVE
> ...


* How to Create Virtual Machines in Linux Using KVM (Kernel-based Virtual Machine)? - GeeksforGeeks  
  https://www.geeksforgeeks.org/how-to-create-virtual-machines-in-linux-using-kvm-kernel-based-virtual-machine/
