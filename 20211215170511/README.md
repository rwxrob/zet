# Kubernetes `wait` for Something

Found this useful command in the `ingress-nginx` instructions. It is
essentially the same as the `wait` command in bash and most other
languages.

```
kubectl wait --namespace ingress-nginx \
  --for=condition=ready pod \
  --selector=app.kubernetes.io/component=controller \
  --timeout=120s
```
