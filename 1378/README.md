# Python JupyterHub in Kubernetes with PyTorch Clusterfuck

Few things prove what a fucking horrible language Python actual is than
the work required to get the NVIDIA PyTorch container image to run in
JupyterHub in Kubernetes. The Dockerfile work is fucking insane because
of all the requirements to first install Anaconda, then Mamba, then
whatever all the dependencies are. 

Imagine for a minute if all this had been done in Go. There would be
one, maybe two compiled binaries with all their dependencies already
resolved, no need to fuck around with grabbing multiple tools just to
setup the framework to pull down more dependencies just to have to fight
with where they all end up and the user permissions involved. 

People can have their shallow opinions for Python without any *actual*
work using the language at scale. That's their right. But I have yet
another pile of objective steaming proof that Python is shit.
Unfortunately, JupyterHub is entirely Python and started as a way to get
Python on the Web. And not I am stuck holding the fucking pile of shit
to get it running in K8S. No wonder no one on planet Earth has gotten
this to work so far (according to multiple Internet searches).

On the bright side, this has given me yet another idea that I could make
into a billion-dollar startup if I wanted to. JupyterHub needs to be
replaced with a JupyterHub compatible turn key solution that is designed
from the ground up for the modern Kubernetes/cloud-native era. It could
still support all the JupyterHub stuff for compatibility, but could even
usher in the new age of Go as the ML replacement for Python, which a few
very selective ML experts have already adopted (which surprised me).
These people realize that the future of large, clunky, disastrously bad
scripting languages that cannot be cross-compiled and easily deployed is
fucking over.

Tags:

    #rants #python #jupyter #cloud #k8s #golang
