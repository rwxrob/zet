# Static Kubernetes Pods

>    Static pods are pods created and managed by kubelet daemon on a
>    specific node without API server observing them. If the static pod
>    crashes, kubelet restarts them. Control plane is not involved in
>    lifecycle of static pod. Kubelet also tries to create a mirror pod
>    on the kubernetes api server for each static pod so that the static
>    pods are visible i.e., when you do kubectl get pod for example, the
>    mirror object of static pod is also listed.


* Whats the difference between \"Pods\" and \"Static Pods\" in kubernetes and when to choose \"static pods\" over regular pods - Stack Overflow  
  https://stackoverflow.com/questions/59612514/whats-the-difference-between-pods-and-static-pods-in-kubernetes-and-when-to
