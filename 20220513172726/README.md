# Just Getting Into Buildah

I don't know how I missed this tool. It is exactly what I've been
looking for to drop my Docker dependency completely and just use
Kubernetes for everything instead of any Docker at all.

> Buildah allows you to have a Kubernetes cluster without any Docker
> daemon for both runtime and builds.

The `buildah` tool from RedHat is a FOSS tool that replaces `docker
build` (which is a pain in the ass if you don't have docker, and
installing docker is harder and harder these days given all the
proprietary shenanigans over at Docker, Inc.). Apparently, it is a part
of `podman` but does not require `podman`.

We've been using `buildah` at work for some things for a while, but I've
never really gotten into it's main use cases.

* GitHub - containers/buildah: A tool that facilitates building OCI images.  
  https://github.com/containers/buildah

* Getting started with Buildah \| Red Hat Developer  
  https://developers.redhat.com/blog/2021/01/11/getting-started-with-buildah

* Buildah and Podman Relationship  
  https://podman.io/blogs/2018/10/31/podman-buildah-relationship.html

    #k8s #buildah #containers
