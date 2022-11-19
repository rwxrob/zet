# Wish: List Kubernetes Resources by StorageClass

Sometimes you want to see everything that is using a specific storage
class in Kubernetes. This requires mapping the PeristentVolumes and
Claims to that StorageClass (which is why it probably has not been
created yet). Such a simple utility is crucial to troubleshooting things
related to a specific storage class, or to Resources that go awry and
don't release their PVC properly (say when you `k delete --force`
something).

Tags:

    #wish #k8s #storage
