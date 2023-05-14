# Amazon Firecracker (microvm) notes

After initial testing it's true, Firecracker is fucking fast! Calling the API against a user-land UNIX socket fired up a VM in under a second. It happened so fast I had to double check the logs to be sure it actually came up. It's so fucking amazing. I'm never using any other virtual machine manager again. Why would I when I can just write `curl` API calls in bash code to bring up any different variation of virtual machines that I want. *Code over configuration!*

1. Startup VMs and vnet with firecracker
2. Configure everything with Ansible that needs it

Hell, if I build the VM images correctly don't even need to sweat the configuration stuff.

Looks like I just need to master the API itself (which is all documented in Swagger style).

## Key points

* "Firecracker is an alternative to QEMU"
* "You can control the Firecracker process via a RESTful API"
* "Firecracker started from Chromium OS's Virtual Machine Monitor, crosvm, an open source VMM written in Rust"
* Critically depends on rust-vmm
* Includes a "jailer" to avoid security failures (eBPF attacks, etc.?)
* Used for the very successful <https://katacontainers.io/> service
* Allows everything I wanted to do with `fluff`
* "only 5 emulated devices are available: virtio-net, virtio-block, virtio-vsock, serial console, and a minimal keyboard controller used only to stop the microVM" (unlike other fatter VMMs)
* "processor agnostic"
* Does ***not*** support any guest operating systems other than Linux (no Windows, etc.)
* Does ***not*** require root to work (absolutely amazing)

Related:

* <https://firecracker-microvm.github.io/>
* <https://github.com/firecracker-microvm/firecracker>
* <https://aws.amazon.com/blogs/aws/firecracker-lightweight-virtualization-for-serverless-computing/>
* firecracker/getting-started.md at main · firecracker-microvm/firecracker · GitHub  
  <https://github.com/firecracker-microvm/firecracker/blob/main/docs/getting-started.md>
* Firecracker and Go Application --- Quickstart \| by Swarvanu Sengupta \| Medium  
  <https://s8sg.medium.com/running-your-go-application-in-firecracker-1c8725cb3910>
