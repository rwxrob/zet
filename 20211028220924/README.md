# Kubernetes Colearning (bare-metal and more)

1. Make the case for on-prem
   * I want to live in a world where on-prem is the priority
   * Cloud computing is fucking expensive -- especially ML
   * Need on-prem to *really* learn infrastructure engineering
1. Here's the hardware I have laying  around
   * 14 Mac Minis
   * 4 MSI Tridents (GPU Nodes)
   * 30-ish assorted Raspberry Pis 
   * 12 low-power laptops
   * Streaming rig
   * 1 Digital Ocean
   * 5 old working phone
1. Let's talk operating systems
   * No cloud-ish operating systems
   * Find a place for OpenBSD for network
   * Enterprise-y
     * Fedora (RedHat)
     * Debian
     * Ubuntu
     * OpenSuse
   * Alpine
   * Raspbian
   * K3OS (RancherOS)
   * Sidero / Talos
   * Arch
   * nixOS
   * Slackware
   * ContainerOS
   * Compile your own (but only later)
     * LFS (grow our own) 
     * Gentoo
1. General architecture
   * Ceph network storage
   * Emulate two availability zones (data centers)
1. Tangent into chaos engineering (and John Deere generator) 
1. I feel a split in my learning strategy
   * Time for raw infrastructure (networking, LFS, netboot, etc.)
   * Time for hardware and node setup
   * Time for CKAD development (operators, redundant pods, ingress, etc.)

Related:

* <https://www.raspberrypi.com/products/poe-hat/>
* <https://www.suse.com/c/suse-linux-enterprise-micro-5-1-is-generally-available/>
* <https://pkgs.alpinelinux.org/package/edge/testing/x86_64/kubernetes>
* <https://pkgs.alpinelinux.org/package/edge/testing/aarch64/kubernetes>
