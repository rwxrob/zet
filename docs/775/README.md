# Actual Issue Opened for `rm -rf /usr` on Install

This [ticket] (which looks legit) is not famous. Someone published an
installer (that runs as root) with the following line in it:

```
rm -rf /usr /lib/nvidia-current/xorg/xorg
```

Aw the pain and suffering adding just one extra space can have. The guy
who made the error said, "Yeah it was really late and I was really
tired." Let it be a lesson to everyone. Don't fucking code when you are
tired! Get some sleep and come back at it.

[ticket]: <https://github.com/MrMEEE/bumblebee-Old-and-abbandoned/issues/123>
