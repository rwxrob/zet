# Getting Linux Root with Grub

Add `init=/bin/bash` to the `linux` line in your Grub boot process after
tapping `e` to edit the current grub config. Should also have to set the
disk to `rw` with `mount / -o rw,remount` (or equivalent). Use `findmnt`
can be really helpful for visualizing the mounts.

* <https://gist.github.com/auwsom/57c4f7c9db585b3f67065f13055986cc>
