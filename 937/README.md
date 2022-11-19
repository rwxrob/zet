# OPA Gatekeeper Fails Over to "Open"

>  Currently, its admission controller can be deployed only as a
>  singleton pod. Without high availability (HA) options, the Gatekeeper
>  webhook defaults to failing “open,” allowing the Kubernetes API
>  server to accept all requests if the admission controller is
>  unavailable. If Gatekeeper’s webhook instead fails to “closed,” write
>  requests made to the cluster API will fail if the controller is
>  unresponsive. HA support is planned for a future release.

I don't know if this has been changed yet or not, but this is a huge bug
in the base design of OPA for Kubernetes. I imagine it is
front-and-center in the list of things to fix (if it has not yet already
been). One can only hope. I'll definitely have this in mind while doing
sample deployments preparing for CKS.

Related:

* Better Kubernetes Security with Open Policy Agent (OPA) - Part 1  
  <https://cloud.redhat.com/blog/better-kubernetes-security-with-open-policy-agent-opa-part-1>

Tags:

    #k8s #opa #fails #devsecops #secops
