# Kubernetes Conventional Metadata Labels

At first I thought these were bloat from the Helm project, then I read
about them on the official kubernetes.io site. Looks like they should be
added to everything and always begin with `app.kubernetes.io/` (see the
docs for the full list). They certainly make `selectors` more specific. 

I've decided to just change `Helm` to `K8SAPP` any time I flatten a Helm
chart.

Related:

* Recommended Labels \| Kubernetes  
  <https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels/>

Tags:

    #k8s #labels #conventions
