# Setting up NFS export for k8s storage class

```
sudo  apt-get install -y nfs-kernel-server
```

All the clients will need `nfs-common`.

```
sudo  apt-get install -y nfs-common
```

Create a new raw disk on machine.

Add a file system to that disk. MAKE SURE CORRECT DEVICE!

```
mkfs.ext4 /dev/sdb
```

Make a mount point.

```
sudo mkdir -p /srv/nfs/k8s
```

Add to `/etc/fstab`


```
/dev/sdb /srv/nfs/k8s ext4 defaults 0 1
```

Add to exports

```exports
/srv/nfs/k8s  *(rw,sync,no_subtree_check,no_root_squash)
```

Restart NFS

```
sudo exportfs -rav
sudo systemctl restart nfs-server
```

Check on it.

```
showmount -e nfs-k8s.local
```

Mount remotely.

```
sudo mkdir /mnt/k8s
sudo mount -t nfs nfs-k8s.local:/srv/nfs/k8s /mnt/k8s
```
