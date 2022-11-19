# Use `parted`/`sfdisk` for Creating Partitions from CLI

> ⚠️
> DO NOT RUN THIS ON ANYTHING YOU ARE NOT TESTING!
> (Easiest is probably creating a VM with volume in Vagrant)

```out
$ sudo parted -s /dev/sdb "mklabel msdos mkpart primary ext4 2048s 100%"
Information: You may need to update /etc/fstab.
```

`-s` forces it without any confirmation so *be careful*.

`/dev/sdb` is the block storage device raw volume.

The commands are surrounded by quotes but don't necessarily have to be.

`mklabel msdos` creates the partition table at the beginning of the
disk.

`mkpart primary ext4 2048s 100%` creates a primary partition (which can
hold other partitions if you want later) that starts at `2048s` (a
standard point after the partition table at the beginning) and fills
`100%` of the disk volume. The `ext4` is optional and informational and
indicates the type of filesystem that is *intended* (but still has to be
formatted with `mkfs`).

Another option, if you prefer an `fdisk` feel is `sfdisk` which is a bit
more complicated but can be scripted with inputs and used to capture and
backup existing partition tables.

Related:

* <https://stackoverflow.com/questions/12150116/how-to-script-sfdisk-or-parted-for-multiple-partitions/12158723#12158723>
* [20220122213646](/20220122213646/) Use `sfdisk` to Backup JSON Partition Tables
