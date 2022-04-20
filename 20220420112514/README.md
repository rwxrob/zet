# Bubye Docker, I Prefer Containerd

Case you haven't heard yet. Docker for Kubernetes is dead, really dead.
Kubernetes 1.24 (due May 5th) ripped out the "shim" support for Docker
engine. Let me say it: you cannot use `docker-ce` for Kubernetes in
version 1.24.

Last time I setup a Kubernetes cluster I used `containerd` since it is
built on the technology from Docker, but it's not Docker. That's a
little confusing at first because some of the packages you have to
install *look* like Docker, but they actually aren't. And you have to
configure everything to not behave like `docker-ce`, which most people
miss and I think that is the reason they go back to Docker.

"Will Docker images still work in Kubernetes?"

Yes, of course, they are just containers. It's the container *engine*
that is being phased out. Docker-ce is not compliant with the Kubernetes
CRI abstraction layer. Kubernetes is becoming more and more of a
standard that defines APIs than an actual thing. In fact, it kinda
always has been that. Kubernetes at the core is a collection of APIs. It
just so happens that some of the "best of breed" implementations have
become the gospel even though they could be replaced with anything (and
`etcd` *really* needs a replacement).

    #kubernetes #docker #containerd
