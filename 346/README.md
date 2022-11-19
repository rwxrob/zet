# Run Docker in a VM on Windows/Mac

Modern containers (Docker) require Linux to run. So you have to install
a virtual machine one way or another. Most don't know that this is
exactly what Docker Desktop and Rancher Desktop do. Why not install
Linux in a light-weight, headless, bridged VM and accomplish the same
thing? Plus, you get full access to a Linux machine and terminal for all
your other needs (not one emulated inside a container).

This approach has the added benefit of allowing you to create the exact
same Linux setup that you would have for a Kubernetes control-plane or
worker node. Why would you throw away that opportunity? Because you are
unable or too lazy to install a container engine as god intended? Fine,
if you are. I'm not.

It is worth mentioning that Docker is proprietary software and the
company continue to surprise the FOSS community with new revelations and
price-tags even though they *barely* wrapped the existing FOSS Linux
container technology in order to create Docker in the first place.
Honestly, other than Docker Hub I find no value in Docker as a company
and want to avoid it whenever possible.

Here are the steps to run containers in a light-weight VM:

1. Install VirtualBox
1. Download Ubuntu Server or Rocky (RHEL) Linux
1. Create a VM that is bridged (if you can)
1. Install `docker-ce` or `containerd` or whatever engine you want
