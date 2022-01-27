# WSL2 Sucks! VMs *or* Containers on Desktop, Not Both

As the world goes container crazy the land of desktop virtual machines
is getting (wrongly) crowded out by the requirements for containers ---
especially on Windows. But, now you can smell the bullshit.

Consider these facts:

* Every single Docker-ish container must run in Linux somehow
* Windows 10 is still required for OSEE certification (for good reason)
* WSL2 does *not* support graphic applications in Windows 10 (11 yes)
* Rancher and Docker Desktop require WSL2 for "optimization"
* WSL2 forces concurrent VirtualBox to suck (if it works at all)
* WSL2 forces VMware Workstation into "hosted" mode
* WSL2 *still* does not work on any system with Cisco Anyconnect
* WSL1 is old and slow (but not hyper-v)

Do you like your chocolate in your peanut butter, or ... Well, you have
to pick one. Just make sure you know what you are getting yourself into.

**Docker in Linux:** If you banish WSL2 from your computer you can run
"hyper" fast VirtualBox/VMware without a problem, host a full graphic
Linux distro, install Docker/Podman/Containerd (take your pick) as god
intended (from the Linux command line), and never know you are running a
Windows machine until it suddenly dies on you for no reason, 'cuz
Windows. But hey, you can still play games, stream with StreamLabs, and
use SolidWorks.

**Linux in Docker:** If all you care about is a Linux terminal (without
all the GUI sugar, and you probably should) then you can do most any job
by just creating a Linux workspace container and use that instead of a
full Linux virtual machine. This option doesn't protect your host
workstation as well and also is extremely annoying since containers are
not persistent by nature, you have to hack in things to keep your files
after you remove your containers, 'cuz containers. But this hassle might
be well worth the savings in system resources otherwise dedicated to a
full virtual machine. Notice I said "full", because if you are using
containers on Mac or Windows you *are* using a virtual machine.

Let's go over that again. **Any container engine on Windows or Mac is
*already* running in a virtual machine.** This is a simple fact that
gets really confusing really quick. Read the next words carefully:
modern containers *only* run on Linux. That's right. Anywhere you are
using a container there is a Linux machine hosting that container, even
if it is well hidden from you. 

> 🤬
> Docker just stole the thunder from the LXC Linux project and got all
> the credit by making it "user friendly."

Since you are *already* required to get Linux on your computer to run
containers you might as well **just install a better virtual machine
yourself** (VirtualBox/VMware/HyperKit) instead of depending on the shitty
ones that come with Docker/Rancher Desktop (if you are a Mac/Windows
user, that is). 

By the way, this is why these "products" are dependent on Windows WSL2,
because WSL2 *is* a Linux virtual machine that Windows ships with its
old and busted operating system to attract the Linux/container crowd. It
is perfectly fine to just say NO to these products and the (broken)
WSL2 and install a real virtual machine instead (as oxymoronic as that
sounds). You'll probably be happier you did in the long run, provided
your computer has enough resources to run a full Linux virtual machine.
(Don't worry, if it can play Fortnite on max settings you will be fine.)

Conclusion: most people should skip "desktop containers" completely and
install a virtual machine if they can. Some companies (like mine)
actively block installs of VirtualBox on any company computer (fucking
morons, it's 2022 for Christ's sake). So you'll have to make your own
educated strategy. But, when in doubt, go with a virtual machine instead
of a workspace container on your desktop. Yes, even if all you do is
machine learning models all day.

Related:

* <https://<linuxcontainers.org/lxc/>

    #linux #containers #desktops #vms #docker #devops
