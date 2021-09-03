# Set Kubernetes Namespace Context

Such a common thing to do that I can never remember.

```
kubectl config set-context --current --namespace=<NS>
kubectl config view | grep namespace
```

Or create a context and use that:

```
kubectl config set-context <CONTEXT> --user=<USER> --namespace=<NS>
kubectl config use-context <CONTEXT>
```
