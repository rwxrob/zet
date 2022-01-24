# Conventional `kubeadm init` Command


> `--apiserver-advertise-address` The IP address the API Server will advertise it's listening o n. If not set the default network interface will be used.


```
kubectl init \
  --apiserver-advertise-address 192.168.2.2 \
```

The following are the implied defaults: 

```
  --pod-network-cidr=192.168.0.0/16
```
