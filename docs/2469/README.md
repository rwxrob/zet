# Using dd on Windows to burn Linux install USB sticks

There's a lot of suggestions out there but the easiest is to install `git-bash` (which comes with all the *actual* utilities that matter including `dd` and then use the `/dev/sd*` notation as revealed from `cat /proc/partitions`.

```sh
rob@tv:/$ cat /proc/partitions
major minor  #blocks  name   win-mounts

    8     0 1000204632 sda
    8     1    102400 sda1
    8     2     16384 sda2
    8     3 999561542 sda3   C:\
    8     4    521216 sda4
    8    16   7864320 sdb
    8    17   7864288 sdb1   D:\
```

Then a good example of dd is something like this:

```sh
sudo dd bs=4M if=/path/to/ubuntu.iso of=/dev/sdX conv=fdatasync status=progress
```

* windows equivalent for dd - Super User  
  <https://superuser.com/questions/839502/windows-equivalent-for-dd>
* cygwin - /dev/sda equivalent in Windows - Super User  
  <https://superuser.com/questions/1204522/dev-sda-equivalent-in-windows>
