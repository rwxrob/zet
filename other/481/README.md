# Multi-Node Kind Clusters Require Config File

Just re-confirmed that (unlike Minikube) there is no command line
argument to create multiple nodes when creating clusters with Kind. The
good news is, that you can specify the name and different images for
these nodes at the same time.

```yaml
apiVersion: kind.x-k8s.io/v1alpha4
kind: Cluster
nodes:
  - role: control-plane
  - role: worker
  - role: worker
  - role: worker
```

In fact, most of the time when using it just makes sense to start with a
`kind.yaml` file and grow with it (sort of like the justification for
`docker-compose.yaml` when working even with single image docker
containerized applications.

Related:

* Getting Started with Kind
  <https://techdozo.dev/getting-started-with-kind-quick-start-a-multi-node-local-kubernetes-cluster/>

Tags:

    #k8s #kind #learning
