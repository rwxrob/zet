# One-Liner to Install Kubernetes NGINX Ingress Controller

I hate Helm. But, sometimes the following is useful when an Ingress is
needed quickly:

```
helm upgrade --install ingress-nginx ingress-nginx \
  --repo https://kubernetes.github.io/ingress-nginx \
  --namespace ingress-nginx --create-namespace
```

You can then create an `ingress` (from the newly added CRD) and install
a demo HTTP server to check it.

```
kubectl create deployment demo --image=httpd --port=80
kubectl expose deployment demo
kubectl create ingress demo-localhost --class=nginx \
  --rule=localhost/*=demo:80
kubectl port-forward --namespace=ingress-nginx \
  service/ingress-nginx-controller 8080:80
```

Related:

* Installation Guide - NGINX Ingress Controller  
  <https://kubernetes.github.io/ingress-nginx/deploy/>

Tags:

    #k8s #nginx #ingress
