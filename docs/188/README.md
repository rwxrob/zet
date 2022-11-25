# PersistentVolumeClaims *Not* in `k get all`

By default, `k get all` will not display a persistent volume claim,
which led me to wonder what was going on all week. I had a feeling it
was using PVC but was trusting `all` to include them, which it was not.
This apparently is a very noob mistake in Kubernetes.
