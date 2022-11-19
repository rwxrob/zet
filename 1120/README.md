# You Cannot Break Shit (As Well) with Docker

I've come to the reality that most of the development and operations
testing requires me to stress systems to their limits to get better
performance and monitor for capacity situations. Well, such things are
simply unsafe to do with an emulated Linux "system" running within a
Docker container. This includes development for things that involve
systems at a lower level in the enterprise architecture (filling a PVC
StorageClass, for example) even though containers are fine for most
other cloud native applications development. Hence Kind.

This means that I have been using Minikube with the `libvirt` driver and
Vagrant a lot more lately as an infrastructure engineer and SRE-type
person. I like writing code that either blows shit up or prevents it
from being blown up. VMs are the only safe playground for that kind of
development.
