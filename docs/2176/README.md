# Learn QEMU, KVM, libvirt, virsh before any other VM tools

As attractive as "microvms" and Firecracker are, it is much more valuable to learn to access the QEMU/KVM systems directly using the tools provided by the Linux teams. These things are always the same and allow creation of *any* virtual machine including those with full device support (such as those needing GPU for ML work, which are not supported by Firecracker currently).
