# Use `cd /c` in Git Bash to Use Windows Files

It's not obvious because `cd /` just shows you the root of the mingw
file system. But `cd /c` will change to Windows and allow you to look at
things like "Program Files ..." etc. You can also do `mount` in Git Bash
to see all your mount points.

```
C:/Program Files/Git on / type ntfs (binary,noacl,auto)
C:/Program Files/Git/usr/bin on /bin type ntfs (binary,noacl,auto)
C:/Users/rob/AppData/Local/Temp on /tmp type ntfs (binary,noacl,posix=0,user temp)
C: on /c type ntfs (binary,noacl,posix=0,user,noumount,auto)
```

    #bash #windows
