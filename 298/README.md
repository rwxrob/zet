# Ports Used in Kubernetes

```
   Master node(s):
TCP     6443*       Kubernetes API Server
TCP     2379-2380   etcd server client API
TCP     10250       Kubelet API
TCP     10251       kube-scheduler
TCP     10252       kube-controller-manager
TCP     10255       Read-Only Kubelet API

   Worker nodes (minions):
TCP     10250       Kubelet API
TCP     10255       Read-Only Kubelet API
TCP     10256       kube-proxy
TCP     30000-32767 NodePort Services
```
