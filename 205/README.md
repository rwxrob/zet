# Kubernetes Services Without a Selector FTW!

> You want to point your Service to a Service in a different Namespace
> or on another cluster.  

Yep, that's what the docs say. This means you can create a Service that
all the other stuff in your cluster sees as being internal that could be
tunneling or proxying *anything* from the outside world. The
possibilities to this are just endless. You could even create a Service
that is tied to a Deployment that periodically caches data from an
Internet source but makes it available internally as a service that can
be queried in any form, sort of like what service workers do in a
Progressive Web Application (PWA). You could also setup an SSH (or
other) concurrent TCP/IP tunnel that automatically heals and creates
another connected (even over the Internet) to *any* TCP/IP server
anywhere.

I really don't have to say more. People who have been around will
immediately realize just how cool "Services without selectors" can be.

Related:

* Service \| Kubernetes  
  <https://kubernetes.io/docs/concepts/services-networking/service/>

Tags:

    #k8s #services #architecture
