# Micro-Virtualization vs eBPF?

After a great conversation yesterday regarding the easiest way to manage
IT infrastructure it seems clear that the future of containerization
will remain strong, but diminish in areas where a microVM makes more
sense. Any time containers are being used as "systems" instead of
applications (as designed) is where the microVM revolution will really
have an affect. Things like Kubevirt will completely die the death it
deserves.


Related:

* microVM: Another Level of Abstraction for Serverless Computing \| by Mostafa Moradian \| ITNEXT  
  https://itnext.io/microvm-another-level-of-abstraction-for-serverless-computing-5f106b030f15?gi=637a2d6e8fd3
* https://firecracker-microvm.github.io/
* What is CRICTL and Why Should You Care?  
  http://crunchtools.com/what-is-crictl-and-why-should-you-care/
* Introducing CRI-O 1.0  
  https://www.redhat.com/en/blog/introducing-cri-o-10
* GitHub - opencontainers/runtime-spec: OCI Runtime Specification  
  https://github.com/opencontainers/runtime-spec (runtime.md, lifecycle)
* The differences between Docker, containerd, CRI-O and runc - Tutorial Works  
  https://www.tutorialworks.com/difference-docker-containerd-runc-crio-oci/
* Solved: podman vs CRI-O vs RunC - Red Hat Learning Community  
  https://learn.redhat.com/t5/Containers-DevOps-OpenShift/podman-vs-CRI-O-vs-RunC/td-p/9639
