# Setting up NFS export for k8s storage class

```
sudo  apt-install -y nfs-kernel-server
```

All the clients will need `nfs-common`.

```
sudo  apt-install -y nfs-common
```

Add to exports

```exports
/srv/nfs/k8s  *(rw,sync,no_subtree_check,no_root_squash)
```

Restart NFS

```
sudo exportfs -rav
sudo systemctl restart nfs-kernel-server
```

Check on it.

```
showmount -e nfs-k8s.local
```
