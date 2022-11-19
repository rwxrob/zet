# Start and Check NFS/RPC Server on Redhat

NFS runs as an RPC service therefore to check for it use the `rpcinfo`
command:

```sh
rpcinfo |grep nfs
```

If it isn't there, it means it hasn't been installed or needs to be
enabled:

```
sudo yum -y install nfs-utils
sudo systemctl enable --now rpcbind
sudo systemctl enable --now nfs-server
```
