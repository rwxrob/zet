# Most Important Aspect of K8S StatefulSet

> STSs schedule stateful pods, which can claim PVs through PVCs and
> mount them as volumes. Once a PV is claimed by an STS replica,
> Kubernetes will make sure that the volume stays with the replica, even
> if the pod gets rescheduled.

Related:

* Reclaiming Persistent Volumes in Kubernetes \| by DataStax \| Building the Open Data Stack \| Medium  
  <https://medium.com/building-the-open-data-stack/reclaiming-persistent-volumes-in-kubernetes-5e035ba8c770>

Tags:

    #k8s #stateful
