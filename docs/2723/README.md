# Notes on installing Kubernetes into home lab

* Install Proxmox
* Create an Ubuntu 24.04 template
* Clone the template into `k8s-node`
* Install `avahi-daemon`
* Clone `github.com/rwxrob/dot`
* Take a VM snapshot

```
sudo apt-get install -y apt-transport-https ca-certificates curl gpg
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.31/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.31/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt update
sudo apt install kubectl kubeadm kubelet
sudo apt-mark hold kubelet kubeadm kubectl
sudo systemctl enable --now kubelet
```

* `jq` (already installed)
* `yq`
