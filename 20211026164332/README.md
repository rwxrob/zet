# Do Not Create Namespaces Beginning with `kube-`

It appears the guys who created our Kubernetes clusters missed the
official documentation that specifically says *not* to every name a
namespace beginning with `kube-` because it is reserved by the
Kubernetes official project. So yeah, `kube-backup` is not a thing to
ever name anything. Now we are stuck with it in prod.

Tags:

    #k8s #bestpractices
