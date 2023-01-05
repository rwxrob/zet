# Kubernetes Port Forwarding

I have found that using the service method is most reliable. Also, I
need to remember that this is only a temporary thing and should not be
used for anything long term (where an actual Ingress should be setup).

```
k port-forward service/harbor-portal 2222:80
```

```
Forwarding from 127.0.0.1:2222 -> 8080
Forwarding from [::1]:2222 -> 8080
```

The first port is the one on the local host machine that can be accessed
from the login user. The target is the second one. 


```
k get service -o yaml harbor-portal
```

Notice how it changed 80 into 8080. 

```yaml
  ports:
  - port: 80
    protocol: TCP
    targetPort: 8080
```

This is because we port-forwarded to a *service* (as you should) and not
directly to a pod, since the IP of any pod could be reassigned at any
time.

Tags:

    #k8s #networking
