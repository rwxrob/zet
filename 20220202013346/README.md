# Getting Alma8 Linux Cloud Images

Once the `qcow2` image is downloaded can be converted to `vmdk` for
VMware with the following command:

```
qemu-img convert -O some.vmdk some.qcow2
```

* https://wiki.almalinux.org/cloud/Generic-cloud.html
* https://repo.almalinux.org/almalinux/8/cloud/x86_64/images/
* https://almalinux.org/es/blog/almalinux-cloud-images-updates-june-18-2021/
* If you want to read more: https://github.com/libyal/libvmdk/blob/main/documentation/VMWare%20Virtual%20Disk%20Format%20(VMDK).asciidoc
