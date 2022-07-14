# Resize Linux LVM Disk with an ext3 Filesystem

Get the name of the logical volume group (VG).

```
sudo vgs
```

```
  VG        #PV #LV #SN Attr   VSize  VFree
  ubuntu-vg   1   1   0 wz--n- 18.22g    0 
```

Expand the logical volume.


```
sudo lvextend -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv
```

Expand the ext3 filesystem.

```
sudo resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv
```
