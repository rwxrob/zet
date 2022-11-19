# Working with Logical Volumes (LVM) in 2022

These days `fdisk` is kinda boomer. Here's some alternatives:

* `pvs` - list physical volumes
* `lvs` - list logical volumes
* `vgs` - list volume groups
* `lvcreate`  - create logical volume
* `lvextend`  - extend existing volume
* `pvcreate` - create physical volume
* `lsblk` - list your block devices
* `blkid` - locate/print block device attributes
* `vdisplay` - display detailed info about volume group

```
root@mini1:~# pvs
  PV         VG        Fmt  Attr PSize    PFree
  /dev/sda3  ubuntu-vg lvm2 a--  <462.71g <362.71g
root@mini1:~# lvs
  LV        VG        Attr       LSize   Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  ubuntu-lv ubuntu-vg -wi-ao---- 100.00g                                         
root@mini1:~# vgs
  VG        #PV #LV #SN Attr   VSize    VFree
  ubuntu-vg   1   1   0 wz--n- <462.71g <362.71g
```

Examples:

Add a 100G volume on a system with free disk in existing LVM volume
group (ubuntu-vg) to allocate:

```
lvcreate -L 100G -n ubuntu-mirror ubuntu-vg
```
