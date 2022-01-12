# Stuff to Remember About Kubernetes Storage

* Everything in Kubernetes (mostly) communicates by IP network
* PV are cluster scoped (never in namespace)
* Adding PV is like plugging in a disk
* PVC always has a name space
* PVC always requires a PV to go with
* PV may get created automatically by SC controller
* With a `manual` PV type *you* are the SC "controller"
* Using `manual` means you have to delete yourself, etc.
* NFS has built-in support in Kubernetes
* PVC in same namespace is automatically mounted in app
* PV claims will be stay after pod delete if ReclaimPolicy Retain
* Retail seems to be default ReclaimPolicy
* Deleting claims manually is a great way to lose all your data
* Even when PVC is deleted, PV shows *last* claim in `k get pv`
* Look at the Status for Released to be sure PV is available
* `k explain` supports dotted notation
* PV cannot be divided with smaller Request PVC, gets all of it
* Best "filled storage" monitoring is Pod using same PV with `du`/`df`
* Only one "monitor" is required per StorageClass (generally)

Recommendations from the community (so far):

* Ceph
* OpenEBS

Related:

* Monitoring Kubernetes PVC disk usage - Stack Overflow  
  <https://stackoverflow.com/questions/64536815/monitoring-kubernetes-pvc-disk-usage>
* Introduction to Kubernetes Persistent Volumes  
  <https://phoenixnap.com/kb/kubernetes-persistent-volumes>
* Monitoring Kubernetes PersistentVolumes · Issue \#2359 · prometheus-operator/prometheus-operator · GitHub  
  <https://github.com/prometheus-operator/prometheus-operator/issues/2359>
* Red Hat Storage Monitoring in Prometheus  
  <https://access.redhat.com/solutions/4406661>
