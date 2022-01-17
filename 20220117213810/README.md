# Ubuntu/PopOS Fix for `libvirt` and `virt-manager`

😃 *Big thanks to @chomkyseal from our Twitch community.*

First make sure you add your user to `libvirt` group and logout and log
back in. You'll know because `groups` will list it and you'll be able to
create VMs using `virt-manager` without any other major changes.

Set `/etc/libvirt/qemu.conf` with following:

```
group = "libvirt"
```

Set `~/.config/libvirt/libvirt.conf` (local user home directory) with
following:

```
uri_default = "qemu:///system"
```

Set `/etc/libvirt/libvirtd.conf` with following:

```
unix_sock_group = "libvirt"
unix_sock_ro_perms = "0777"
unix_sock_rw_perms = "0770"
auth_unix_ro = "none"
auth_unix_rw = "none"
```

⚠️  ***MAKE SURE YOU `sudo systemctl stop libvirtd` and `sudo systemctl start libvirtd` to be absolutely sure it restarts.***

Related:

* [20220113174634](/20220113174634/) Learning Lab: Setup Qemu Virtual Machine on Linux
* [20220115035315](/20220115035315/) Lookup Default Volume Used by QEMU/KVM
* [20220117193026](/20220117193026/) QEMU, KVM, XEN, `libvirt`, and `virt*`
* [20220113202907](/20220113202907/) Proxmox with Terraform at Home

Tags:

    #popos #ubuntu #kvm #bugs #libvirt #qemu
