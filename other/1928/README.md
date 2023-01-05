# Forward x11 display through ssh

First you have to enable it in the `/etc/ssh/sshd_config` file (note the d).

```
X11Forwarding yes
```

Then you have to remember to add the right switches to the `ssh` command:

```sh
ssh -X -Y you@remote
```

You shouldn't have to mess with the DISPLAY variable at all.

* Forwarding X11 Apps through SSH - Linux.com  
  <https://www.linux.com/training-tutorials/forwarding-x11-apps-through-ssh/>
