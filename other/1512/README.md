# Kubernetes On-Prem, Batteries *NOT* Included

> "Kubernetes does not offer an implementation of network load balancers
> (Services of type LoadBalancer) for bare-metal clusters"
>
> "The implementations of network load balancers that Kubernetes does
> ship with are all glue code that calls out to various IaaS platforms
> (GCP, AWS, Azure…). If you’re not running on a supported IaaS platform
> (GCP, AWS, Azure…), LoadBalancers will remain in the “pending” state
> indefinitely when created."

The following are *not* included in any Kubernetes installation by
default, and so there are some default implementations that people tend
to use:

* Ingress (`ingress-nginx` or `traefik`)
* LoadBalancer (`metallb`)

Related:

* <https://kind.sigs.k8s.io/docs/user/loadbalancer/>

Tags:

    #k8s #onprem #batteries
