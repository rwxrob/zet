# 💡 Add `vmrun` command for VMware from git-bash on Windows

VMware comes with many command line utilities that aren't always documented well. One of my favorites is `vmrun.exe`, but it needs a bit of help to make it useful. This function starts up a virtual machine matching the name passed as the first argument. The VM is started without the GUI, but the GUI can be easily accessed from the VMware client GUI if needed.

```sh
vmrun ()
{
    "/c/program files (x86)/vmware/vmware workstation/vmrun.exe" -T ws start "$HOME/documents/virtual machines/$1/$1.vmx" nogui
}
```

Don't ask me why VMware decided to put their default location for virtual machines under "documents". 🤦

By using this, I only need two commands from my `git-bash` terminal after starting my Windows desktop.

```sh
$ vmrun anton
$ ssh anton
```

And if I shutdown my computer properly I can even `tmux a` to reestablish exactly where I was in my TMUX session.
