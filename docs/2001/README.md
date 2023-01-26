# Check content of a Kubernetes PVC PersistentVolumeClaim

```yaml
#!/bin/bash
CLAIM=$1
cat <<EOF | kubectl apply -f -
apiVersion: v1
kind: Pod
metadata:
  name: pvc-inspector
spec:
  containers:
  - image: busybox
    name: pvc-inspector
    command: ["tail"]
    args: ["-f", "/dev/null"]
    volumeMounts:
    - mountPath: /pvc
      name: pvc-mount
  volumes:
  - name: pvc-mount
    persistentVolumeClaim:
      claimName: $CLAIM
EOF
```


* Inspect a Kubernetes PersistentVolumeClaim \| Frank Sauerburger  
  <https://frank.sauerburger.io/2021/12/01/inspect-k8s-pvc.html>
* docker - how to inspect the content of persistent volume by kubernetes on azure cloud service - Stack Overflow  
  <https://stackoverflow.com/questions/49529005/how-to-inspect-the-content-of-persistent-volume-by-kubernetes-on-azure-cloud-ser>
