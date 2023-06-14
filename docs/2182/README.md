# Many tmpfs files are reset when `start -a` to existing container

Update: turns out this is because `/etc/hosts` is a **bind mount** (which I created another zet about).

I was shocked to learn that local modifications to `/etc/hosts` were lost after exiting and later `podman start -a ws` to reconnect. I had added them so that `ssh` would do tab completion (which can also be accomplished in other ways). I discovered (after a friend told me) that `/etc/hosts` is actually a `tmpfs` type that is reset upon ever `start` (restart) of the container. In other words, changes are not persisted.

```
tmpfs on /dev type tmpfs (rw,nosuid,noexec,size=65536k,mode=755,uid=1000,gid=1000)
tmpfs on /etc/hosts type tmpfs (rw,nosuid,nodev,relatime,size=1302836k,nr_inodes=325709,mode=700,uid=1000,gid=1000)
tmpfs on /run/.containerenv type tmpfs (rw,nosuid,nodev,relatime,size=1302836k,nr_inodes=325709,mode=700,uid=1000,gid=1000)
tmpfs on /run/secrets type tmpfs (rw,nosuid,nodev,relatime,size=1302836k,nr_inodes=325709,mode=700,uid=1000,gid=1000)
shm on /dev/shm type tmpfs (rw,nosuid,nodev,noexec,relatime,size=64000k,uid=1000,gid=1000)
tmpfs on /etc/hostname type tmpfs (rw,nosuid,nodev,relatime,size=1302836k,nr_inodes=325709,mode=700,uid=1000,gid=1000)
tmpfs on /etc/resolv.conf type tmpfs (rw,nosuid,nodev,relatime,size=1302836k,nr_inodes=325709,mode=700,uid=1000,gid=1000)
cgroup on /sys/fs/cgroup type tmpfs (rw,nosuid,nodev,noexec,relatime,size=1024k,uid=1000,gid=1000)
tmpfs on /proc/acpi type tmpfs (ro,relatime,size=0k,uid=1000,gid=1000)
tmpfs on /sys/firmware type tmpfs (ro,relatime,size=0k,uid=1000,gid=1000)
tmpfs on /sys/dev/block type tmpfs (ro,relatime,size=0k,uid=1000,gid=1000)
```
