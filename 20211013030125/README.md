# Minikube Disk Limitations are Annoying

I'm really starting to see why so many people prefer Kind over Minikube
these days for most work. I keep hitting the out of space issues with
Minikube either in terms of disk or memory. These issues never come up
with Kind because it does everything in the local host container engine,
which has unlimited space. I'm sure there's a way around it when you
setup the Minikube cluster, but it is annoying that you have to do it at
all.

I can see why Minikube is a more realistic lab environment because it
actually contains a container engine within the virtual machine. But
when I'm already using and extending the image in the host system
getting it into the docker container engine within the Minikube VM is a
royal pain in the ass. "It's right there! Just use it."

Tags:

    #kind #minikube #k8s #tools

