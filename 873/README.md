# Cloud Images are Bad for Beginner Training

I just booted up a Rocky cloud image and realized the only way to get
a password on it was setting up `cloud-init` or dropping to the init
shell, disabling selinux, and editing the password file, true hacking
skills to be sure, but absolutely not for beginners.

Then after reading some recommendations out there I looked for the
"minimal" versions to essentially do the same but with an ISO image.
Ubuntu has entirely dropped support for their minimal image (so you
can't even find it) and Rocky and Alma have it, but they don't boot with
any network activated by default. That's right. You have to edit the
network configuration files or use `ifconfig` to being *any* networking
up at all. Again, definitely *not* beginner stuff, at least not
beginners who are just getting a handle on all the tools, processes, and
basic programming needed before getting into all of those details.

So I am broading the amount of time spent on getting the immediate tools
into the skill stacks of those doing the Boost, which includes both Kali
Linux as an example of a GUI virtual machine, and Ubuntu server after
that (which will still need network configuration).
