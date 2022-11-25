# Containerd vs CRI-O

This is a place to summarize difference between the two biggest container engine competitors (k8s 1.24 requires one or the other):

**Containerd** is a full drop-in run-time replacement for **docker**, **CRI-O** is not. There is no way to run a container with CRI-O. Containerd comes with `ctr` but it is not at all like `docker`. I hear good things about `nerdctl` which is supposed to be more like `docker` command.

CRI-O has big backing and support from IBM, RedHat, Intel, SUSE and lots of other enterprise-y things, containerd is driven by Docker and a broader, more FOSS-y community.

CRI-O was specifically designed and optimized for k8s, containerd for docker, it's important to note that Docker (as a company) has been through many financial troubles and business problems and frankly should not be considered stable, at all, the founder left "to pursue other interests".

Containerd is simpler with usability as a priority; CRI-O is more complex, maybe faster, but less focused on usability.

Containerd does not have specific versions compatible with specific k8s versions; CRI-O was so buggy it was unusable before 2022 but seems better now even though different versions of CRI-O are still required for different k8s version, but k8s 1.24 (which banishes docker entirely) is a huge milestone and will be the baseline for a long times

Both end up running containers using runc (libcontainer written in Go).

Sources:

* Containerd vs CRI-O  
  <https://phoenixnap.com/kb/docker-vs-containerd-vs-cri-o>

* The differences between Docker, containerd, CRI-O and runc - Tutorial Works  
  <https://www.tutorialworks.com/difference-docker-containerd-runc-crio-oci/>

* Solomon Hykes Leaves Docker » Linux Magazine  
  <https://www.linux-magazine.com/Online/News/Solomon-Hykes-Leaves-Docker>

* Docker founder launches Dagger, a new DevOps platform -- TechCrunch  
  <https://techcrunch.com/2022/03/30/docker-founder-launches-dagger-a-new-devops-platform/>

* Why and How to Use containerd From Command Line  
  https://iximiuz.com/en/posts/containerd-command-line-clients/
