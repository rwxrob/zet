# Stuff to Remember About Kubernetes Storage

* Everything in Kubernetes (mostly) communicates by IP network
* PV are cluster scoped (never in namespace)
* Adding PV is like plugging in a disk
* PVC always has a name space
* PVC always requires a PV to go with
* PV may get created automatically by SC controller
* With a `manual` PV type *you* are the SC "controller"
* NFS has built-in support in Kubernetes
* PVC in same namespace is automatically mounted in app
* PV claims will be left behind if you use Pod/Deployment
* PV claim cleanups are governed by the ReclaimPolicy on Volume
* Deleting claims manually is a great way to lose all your data
