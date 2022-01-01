# Ceasing All Research for Windows WSL2 Workstation

I've concluded that further work supporting and researching how to do
anything on Windows systems is simply out of scope until the critical
flaws are fixed that block Anyconnect VPN from working with WSL2 out of
the box. 

The workarounds are currently horrible and usually involve hacking in an
extra PowerShell script. Others have transformed their laptops into
proxy-routers (essentially) and use their own hardware. These
"solutions" are not only not complicated and somewhat unnatural but
usually supported and against the IT policies of the enterprises that
require this broken VPN setup. 

Therefore, I will no longer be doing any further research or publishing
anything that promotes the use of Windows as a Linux alternative. What
good is WSL2 if it cannot be used in *most* enterprise environments by
remote employees required to use VPNs? Until this is resolved officially
by a collaboration between Microsoft and Cisco I will do everything in
my power to ensure that the warning goes out and that people actively
campaign --- in every way possible --- for this to be fixed. But the
issue has been on GitHub for over two years with no hope of resolution
in site, so I'm not hopeful.

This is particularly important since Docker Desktop is proprietary and
requires organizations over 250 to pay a price per seat to use it.
Docker Desktop is the only proven way to use all the standard tools ---
without modification --- and still use Linux on Windows by creating a
workspace container (as I have used at work for most of the last year).
This has killed any hope of getting a supported Docker solution, that
does not cost extra money, working and the reason the company I work for
has actively moved *away* from Windows for their machine learning
workstations going with Mac instead. (They are still to unsupportive of
Linux on workstations because of how conservative they are.)

Related:

* [20210505174119](/20210505174119/) Install WSL2 for Docker Desktop on Windows
* [20210701203752](/20210701203752/) Fix WSL2 Cisco AnyConnect VPN Failures
* [20210909140020](/20210909140020/) Use `minikube` Instead of WSL2 and Docker Desktop

Tags:

    #windows #linux #wsl2 #fails #vpn
