# QEMU, KVM, XEN, `libvirt`, and `virt*`

I've been confused by the relationship between the core components of
Linux virtualization. I think this is how they are related:

**KVM is the lowest level (a type 2 hypervisor)** to the Linux kernel
and requires a reboot to update when a change is made (although people
claim that you do not and you only need to when you install it,
sometimes it is just `libvirtd` service that needs a restart). KVM
effectively replaces XEN (as Amazon has done).

**QEMU is application "in user space" that provides emulation for many
machine architectures** including ARM simulation on x86 machines and
talks to the kernel through KVM.

**`libvirt`/`libvirtd`/`virsh` is a virtualization management library
that uses any one of several virtualization methods** including KVM,
XEN, ESXi, QEMU (and many others).

I've been told that comparing KVM and XEN code in the kernel source can
be a way to understand the difference.

Related:

* [20220121191334](/20220121191334/) 🖼️  Libvirt, QEMU, KVM, XEN, VMware, VirtualBox
* The Geeky Way -- KVM vs QEMU vs Libvirt  
  <https://www.thegeekyway.com/kvm-vs-qemu-vs-libvirt/>
* linux/kvm_main.c at master · torvalds/linux · GitHub  
  <https://github.com/torvalds/linux/blob/master/virt/kvm/kvm_main.c#L18>
* linux/kvm_main.c at master · torvalds/linux · GitHub  
  <https://github.com/torvalds/linux/blob/master/virt/kvm/kvm_main.c#L18>
* <https://www.arthurkoziel.com/running-virt-manager-and-libvirt-on-macos/>
