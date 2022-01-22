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

Related:

* <https://stackoverflow.com/questions/12150116/how-to-script-sfdisk-or-parted-for-multiple-partitions/12158723#12158723>
* [20220122213646](/20220122213646/) Use `sfdisk` to Backup JSON Partition Tables
