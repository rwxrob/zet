# Local Kubernetes Kind Persistent Volumes

Sometimes you need to test storage without all the hassle of using a
StorageClass provider or NFS (even though you can also do that locally
for a closer setup to the real thing).

> ⚠️ 
> You *cannot* create a PersistentVolume from the command line.  A YAML
> resource file is required.

Related:

* Configure a Pod to Use a PersistentVolume for Storage \| Kubernetes  
  <https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/>
* Kind Persistent Volumes  
  <https://mauilion.dev/posts/kind-pvc/>
