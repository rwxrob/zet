# eBPF Allows Programs to Execute Code in Kernel

This is big because it provides safe (sandboxed) access to stuff
normally only a kernel module (think `modprobe`) would have, like
networking layer stuff, low-level permissions, and kernel-level logging.
This has implications for cloud-native as well since it could be
possible that cloud applications actually can configure the very
kernel-level behavior of a node (machine). Right now, OSes like
OpenShift's CoreOS, K3OS, FlatCar, and Rancher (to some degree) all take
a more drastic approach to associating the host system (node) with the
kubernetes endpoint running on it. But tech like eBPF might affect that
in the future.

* [A Gentle Introduction to
eBPF](https://www.infoq.com/articles/gentle-linux-ebpf-introduction/)
