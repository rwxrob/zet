# Kind Service Mapping Sucks Compared to Minikube

Perhaps the hardest thing for beginners to get their heads around is all
the networking magic that Kubernetes requires. The last thing any
beginner wants is to have to do all the mental model of port forwards
and exceptional cases where networking is entirely different, yet this
is exactly what Kind requires (see the issue in Related). Minikube, on
the other hand, does exactly what you would expect, magically mount any
service automatically and provide a `minikube service <service> --url`
command to get the exact web address of the service. This brilliance
cannot be overstated. It saves you the immense hassle of setting up a
full ingress or customized port forwarding mechanism.

I won't get into all the problems with how Kind does this, nor the fact
that it is entirely different on Linux from Mac and Windows because you
don't have to worry about any of that on Minikube. For example, say you
are setting up JupyterHub in Kubernetes locally and want to test some
custom images (I'm actually preparing a PyTorch image). JupyterHub
requires the creation of a LoadBalancer during Helm install. Now
consider that the port of the LoadBalancer is not known at the time the
Kind/Minikube cluster is created. There is no possible way to know that
in advance. (Actually, you can lock down that port in your Helm config,
but that is cheating.)

In short, Kind networking is fundamentally broken by forcing you to
either only use resources and configuration that allow you to lock down
and know all the ports in advance, or create your own elaborate ways of
mapping all the service ports and forwarding them *after* the cluster is
created. Just like good 'ol `docker` requires knowing all the port
forwards in advance before running an image, we hit a similar problem
with Kind. Minikube gets around all of this by including as a high
design priority the automatic mapping of all services to IP addresses
and ports that are available from `minikube services` command.

I *really* wish the community could come together on this stuff. It is
seriously fucking annoying having one thing work in one localized k8s
tool and another not. In short, for most of the complicated networking
work that I'm doing I will be reaching (back) to Minikube for this stuff
instead of Kind. But let it be known, this isn't me flip-flopping, it's
the Kubernetes community itself. Just search out the forums
debating all this. There is zero consensus and a lot of "we should
probably add that eventually" which is absolutely infuriating.

Related:

* <https://github.com/kubernetes-sigs/kind/issues/99>
* kind -- Configuration  
  <https://kind.sigs.k8s.io/docs/user/configuration/#extra-port-mappings>

Tags:

    #k8s #kind #minikube #networking
