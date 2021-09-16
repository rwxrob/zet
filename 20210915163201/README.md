# Minikube Automatically Routes LoadBalancer

If your Helm chart includes a LoadBalancer then minikube appears to
detect it and provide its own Ingress, meaning that you get access the
Service with just the URL provided by `minikube service NAME --url` even
if the 'EXTERNAL IP' is listed as `pending`:

```
NAME           TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
hub            ClusterIP      10.104.112.147   <none>        8081/TCP       21h
kubernetes     ClusterIP      10.96.0.1        <none>        443/TCP        21h
proxy-api      ClusterIP      10.99.35.163     <none>        8001/TCP       21h
proxy-public   LoadBalancer   10.111.74.248    <pending>     80:31831/TCP   21h
```

The `pending` still works:

```
$ mk service proxy-public --url
http://192.168.99.100:31831
```

You can just open up that URL (with port) in a web browser and get to
your service.

    #k8s #minikube #services #routing
