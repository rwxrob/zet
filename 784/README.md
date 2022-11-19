# I Was Wrong. Docker Compose Rocks!

I was creating a `build` shell script for everything and realizing all
of the stuff in there was already covered by one of the `docker-compose`
actions in a much better way.

Also, after using Kubernetes for over eight months, and dealing with K8S
applications, and discovering `kompose` and `kubectl kustomize` and
realizing how *horrible* Helm is, I now strongly believe building an
application in `docker-compose` *first* should be considered a best
practice for building Kubernetes applications later. Not only does this
allow your application to be consumed by more people (including those
not using any container orchestration) but it provides a solid, simple,
stepping stone up to a full Kubernetes application as a part of the
process.

Adding a `docker-compose.yaml` (I refuse to use `.yml`) is also a great
way to demonstrate how your single image can be used. I included the
defaults in the file so people can look at it quickly and see what is
going on.

Another advantage is that you can distribute your application to people
easily who do not have Kubernetes (and may never have it).

Tags:

    #k8s #docker #compose
