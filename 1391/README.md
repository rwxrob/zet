# Kuberbetes pause Container Sets Up Networking

 The "pause" container is a container which holds the network namespace for the pod. Kubernetes creates pause containers to acquire the respective pod’s IP address and set up the network namespace for all other containers that join that pod.

* [docker - What are the pause containers? - Stack Overflow](https://stackoverflow.com/questions/48651269/what-are-the-pause-containers)
* [The Almighty Pause Container - Ian Lewis](https://www.ianlewis.org/en/almighty-pause-container)
* <https://groups.google.com/forum/#!topic/kubernetes-users/jVjv0QK4b_o>
