# Use `kind load` Instead of Private Repo

One of the mistakes that I made when starting with Kubernetes/Kind was
assuming I needed a local repository from which to pull stuff for my
cluster. I really wish I had read all of the minimal `kind` command
explanations --- particularly `kind load` which loads a docker image
into the node(s) of the cluster thereby removing the need for a
repository at all. Then if you actually need a private cluster as part
of the development, say if you are making something that requires
pointing to one, you can do it with the Kind registry plugin, which
just reuses the current container engine as if it were a private
registry.

Tags:

    #k8s #kind #tips
