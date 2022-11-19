# Back to Kind for Everything Kubernetes

After finally taking the time to learn how to add MetalLB and NGINX
Ingress to Kind I won't be returning to Minikube any time soon for my
local single-node work. I have them both bundles as K8SAPPs so it should
be really easy to add, but I'm going to make a script that wires up a
new Kind cluster with all of that automatically, which is essentially
what Minikube has been doing with it's plugin. I prefer using *real*
implementations that I would encounter in the wild instead of
replacement plugins.

I really wish all those recommending Kind to me early on had recommended
this and made sure to emphasize that I learn Kubernetes networking
before *anything* else.

Related:

* <https://kind.sigs.k8s.io/docs/user/loadbalancer/>
