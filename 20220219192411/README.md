# Warning: WSL2 Fucks Up Git Repos

Today I disabled WSL2 and rebooted and now I can't commit objects to my
zet repo. The only thing that changed was removing WSL2, which I'm
almost positive is fucking with the filesystem somehow. There is no
fucking way I will ever trust Windows to do the right thing with
Linux-to-Windows filesystems again. STAY THE FUCK OFF OF WSL2!

```
error: object file .git/objects/08/6f648bca59894842992f8493c208309938878c is empty
fatal: loose object 086f648bca59894842992f8493c208309938878c (stored in .git/objects/08/6f648bca59894842992f8493c208309938878c) is corrupt
```

    #rant #wsl2 #linux
