# Use `parted` for Creating Partitions from CLI

> ⚠️
> DO NOT RUN THIS ON ANYTHING YOU ARE NOT TESTING!
> (Easiest is probably creating a VM with volume in Vagrant)

```
parted /dev/sdb "mkpart primary 2048s 100%"
```

Keep in mind, this does not allow you to do special stuff like make it
bootable (or set the MBR).
