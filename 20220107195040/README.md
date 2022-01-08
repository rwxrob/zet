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
