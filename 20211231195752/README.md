# Ceasing All Research for Windows WSL2 Workstation

***Update: I was a complete idiot for thinking WSL2 would even be
stable. Not only is it remarkably laggy and slow (I have tons of video
evidence of it) but it has several other major drawbacks. In fact,
removing it actually corrupted one of my git repos that has some crazy
shit going on with the filesystem. STAY THE FUCK AWAY FROM WSL2!***

* [20220211021943](/20220211021943/) Weird Permissions Error in WSL2
* [20220219042322](/20220219042322/) Things WSL2 Can Do That Local VM Cannot
* [20220219043128](/20220219043128/) Things Local VM Can Do That WSL2 Cannot
* [20220219192411](/20220219192411/) Warning: WSL2 Fucks Up Git Repos

***Update: I overreacted to VPN not working in WSL2. I've since decided
to use WSL2 as my daily driver because outside of this VPN problem, WSL2
really is the best Linux desktop distro for most working people.***

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
* [20220128164251](/20220128164251/) Windows WSL2 is the Best Linux Desktop of 2022

Tags:

    #windows #linux #wsl2 #fails #vpn
