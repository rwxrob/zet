# Istio and internal DNS mandatory for Kubernetes homelab

Just ran into a situation at work that can only be tested safely from a completely disconnected home lab network that has its own internal DNS, Kubernetes installation, and Istio installed into the cluster. It is really quite a basic thing to want to do: setup a VirtualService pointing to a CNAME for the name host rather than a route. In my case, it is for the MkDocs server running in "dev mode" so that it automatically updates from a git repo when fetched with a CronJob (which turns out to be required to meet the https standard since MkDocs in dev mode *does not support certificates at all*.

```
docs.my.example.com -> mkdocs.prod.svc.cluster.local
```

The problem is that in order to test different VirtualService configurations based on host names (CNAMES) I am required to get the CNAME record added by the networking team and propagated before I can even test the thing. This turn around time is impossibly slow in an environment where multiple applications are being setup with CNAME/subdomains instead of routes. The *only* way to test it reliably is to change it in a local network with DNS properly setup and under my control to test it.

You could say that this argues against the use of CNAME/subdomains for things like this, and you'd be right, but that doesn't remove the need to be able to test it when required.

* Istio / Virtual Service  
  <https://istio.io/latest/docs/reference/config/networking/virtual-service/>

