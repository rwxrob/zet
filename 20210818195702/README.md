# Thoughts on Cloud Native Learning Plan

Having made a lot of mistakes in my approach to learning this cloud
native stuff I want to share my lessons learned about the order of stuff
to learn such that it will make the most cohesive sense to absolute
beginners. Of course, I assume people have everything from the *Live
Linux Terminal* boost already. (You don't realistically have a prayer
with this stuff until you can call youself a "Linux terminal native".)

You should be able to add the following skills in order:

1. Grok *Container*
1. Use `docker` command to pull, run, and push images
1. Be able to mount volumes and expose networking in docker
1. Create your own `Dockerfile`images 
1. Install Kubernetes `kind` cluster (or other local cluster)
1. Use and grok `kubectl config`
1. Grok *Pod*
1. Use `kubectl run` (almost same as `docker run`)
1. Use `kubectl get pods`
1. Grok *Deployment*
1. Grok *ReplicaSet*
1. Use `kubectl create deploy`
1. Use `kubectl exec`
1. Use `kubectl desc`
1. Use `kubectl logs

The main point I wanted to point out is that it was not immediately
obvious to me that `kubectl` has almost exactly the same commands as
`docker` for dealing with single pods (usually one container).
Capitalizing early on this similarity will really help beginners.

In fact, one thing I have found extremely useful is to use `kubectl`
locally (with `kind`) instead of `docker` for things that I might
otherwise use just Docker for instead, which ends up being very nice
because you can immediately do things that Docker just can't.

In fact, replacing any learning of `docker-compose` immediately with
using `kubectl` locally will benefit most people the best in the long
run. For example, creating a set of YAML (or single file) and creating
a small deployment locally is *always* better than docker compose
because that skill immediately translates into k8s work.

See also:

* <https://github.com/rwxrob/boost>

    #cncf #learning #k8s #planning #education #devops
