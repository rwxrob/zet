# `podman` Adds `systemd` to All Containers

This write up from an engineer at Red Hat outlines the single most compelling reason I have ever heard for using `podman`: it actually initializes and uses `systemd` within the container by default.

You might hate `systemd` but it doesn't matter. It is the most prevalent `init` system on the planet at this point and is a pain in the ass to get running in a container because of how fucking stupid it is. This is outlined very well in the related blog post. So you can imagine my surprise when I read in that same post that `podman` magically takes care of all that shit and includes `systemd` automatically. The amount of headache that removes is enormous.

Now I have a tough decision to make: to continue to do my Kubernetes in Docker setup with all the tweaking required to get `systemd` to work so that `kubeadm init` will work, or to just start the whole lab by saying "This lab requires that you install `podman`."

Of course, there is always the option of doing everything from a VM and creating a separate VM for every node. That way you get `systemd` as a part of the OS, obviously.

Related:

* How to run systemd in a container \| Red Hat Developer  
  <https://developers.redhat.com/blog/2019/04/24/how-to-run-systemd-in-a-container>
