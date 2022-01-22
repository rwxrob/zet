# Use `parted`/`sfdisk` for Creating Partitions from CLI

> ⚠️
> DO NOT RUN THIS ON ANYTHING YOU ARE NOT TESTING!
> (Easiest is probably creating a VM with volume in Vagrant)

```
parted /dev/sdb "mklabel msdos; mkpart primary 2048s 100%"
```

Another option, if you prefer an `fdisk` feel is `sfdisk` which is a bit
more complicated but can be scripted with inputs and used to capture and
backup existing partition tables.

One cool thing about `sfdisk` is exporting a partition table to JSON.

```
sfdisk /dev/sda -J
```

```out
{
   "partitiontable": {
      "label":"dos",
      "id":"0x00000000",
      "device":"/dev/sda",
      "unit":"sectors",
      "sectorsize":512,
      "partitions": [
         {"node":"/dev/sda1", "start":32, "size":61341664, "type":"c"}
      ]
   }
}
```

Related:

* <https://stackoverflow.com/questions/12150116/how-to-script-sfdisk-or-parted-for-multiple-partitions/12158723#12158723>
