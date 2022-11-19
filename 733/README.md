# Weird Permissions Error in WSL2

Went to move my `dot` files out of the way in order to download a
rebased repo and ran into the strangest problem in WSL2 that I've
experienced to date. I was simply denied doing anything to my own
directory even with sudo. I had to delete the entire thing and replace
it, which makes me super glad that I maintain all of this stuff in Git
repos.

```
drwxr-xr-x 1 rwxrob rwxrob 4.0K Feb 10 21:14 ./
rwxrob.tv:rwxrob$ pwd
/home/rwxrob/Repos/github.com/rwxrob
rwxrob.tv:rwxrob$ ls
boost     cmd-zet        conf-go  fluff  live    rwxrob.github.io  zet
cmd-clip  cmdbox         cv       fonts  rwx.gg  vm
cmd-live  cmdbox-config  dot      lab    rwxrob  workspace
rwxrob.tv:rwxrob$ sudo mv dot dotsome
mv: cannot move 'dot' to 'dotsome': Permission denied
```

    #quirks #wsl2 #linux #windows
