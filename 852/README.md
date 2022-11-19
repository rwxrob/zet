# Conclusions About Home Lab Server

I've been conflicted about how much hardware I need and how to deploy it
in a way that will be the most flexible when testing radically different
simulations of full IT deployments. For example, Icinga doesn't run well
in Kubernetes but I need to test talking to it from within a Kubernetes
application that keeps eyes on PVC and a StorageClass. That means at
number of VMs just for the simulated Kubernetes cluster and a few for
the things needed in the environment, "external DNS" (for load
balancing), and the host systems for Icinga.

I thought I could do this with just all the old hardware I have laying
around, but the realization the "over-provisioning" allows virtual
machines to share a single CPU has opened my eyes to the possibility of
a single, multi-core, lots-of-RAM (which can't be over-provisioned)
machine. Obviously, System76 machines came to mind and are a great
example of what I need eventually, but the cost is prohibitive and
possibly something that I could get them to sponsor.

In the meantime, I'll see how far I can push this 8-core MSI server
(gaming) tower. Perhaps it will be enough (at least until I can convince
System76 to sponsor me and at least cut the price of one of their rigs,
give me one for free, or even pay me and give me one, I can only dream).
