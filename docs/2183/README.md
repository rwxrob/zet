# Bind mounts are glorified hard links that work with files

It's a simplification for understanding it. It's actually a lot more complicated (and involves **virtual file systems**). This is likely the origin of Kubernetes ConfigMaps being able to mount "volumes" that are individual files.

This is actually documented under `--bind` in the `mount` command man page:

> One can also remount a single file (on a single file). It’s also possible to use a bind mount to create a mountpoint from a regular directory, for example:
>
>    `mount --bind foo foo`

I tried the example of bind mouting `/etc/passwd`. First, I had to create a file (not a directory) at the target:

```sh
touch /mnt/mypasswd
```

Then give the `--bind` option (or `-o bind` equivalent) to the `mount` command:

```sh
mount --bind /etc/passwd /mnt/mypasswd
```

The `mount` command shows something that might confuse someone who doesn't understand bind mounts:

```
/dev/sda2 on /mnt/mypasswd type ext4 (rw,relatime)
```

This gets even more confusing when listing block devices with `lsblk` where this shows up as a "partition" type.

```
sda      8:0    0 476.9G  0 disk
├─sda1   8:1    0     1G  0 part /boot/efi
└─sda2   8:2    0 475.9G  0 part /mnt/mypasswd
```

The `sda2` is actually *created* just for that single file mount even though it has identical size it has a different device minor:major number. This stuff is in `/proc/self/mountinfo` as well.

```sh
# grep passwd /proc/self/mountinfo
154 29 8:2 /etc/passwd /mnt/mypasswd rw,relatime shared:1 - ext4 /dev/sda2 rw
```

The `findmnt` command will show which mounts are files.

```sh
# findmnt |grep passwd
├─/mnt/mypasswd                               /dev/sda2[/etc/passwd] ext4        rw,relatime
```

So bind mounting is like filtering out specific directories---or a single file---from a base, existing filesystem and only making it available as a mountable filesystem itself.
