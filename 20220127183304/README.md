# Switching from Linux to Windows for Streaming

I've been forced recently to reorganize all the computers I use for work
and play. Here are some surprising conclusions leading to the decision
to switch from Linux to Windows workstation (with no WSL) and full Kali
Linux virtual machine as my daily driver:

**Personally, I just need a Linux terminal** that's it. I don't give a
shit how I get it so long as it is responsive and I can put TMUX on it.

**Kali Linux Desktop attracts the most followers to stream** and
prepares me and others best for a career that involves Linux since it is
-- by far -- the best first Linux experience for those wanting to learn
Linux as a professional tool. It's also currently the prettiest Linux
distro out of the box. In full screen mode people watching the stream
won't even realize I'm not running Kali on my hardware -- especially
since I'll be running it from VMware Workstation Pro and/or VirtualBox.

**WSL2 is a fucking disaster** meaning that nothing that requires or
installs it will have any place on my systems. It blocks too many other
important applications from working *effectively* such as VirtualBox and
Vagrant and Cisco Anyconnect VPN and any application with any graphics
at all (10 is better than 11). It's really sad that WSL2 is still just
so fucking bad. Not working with Cisco Anyconnect makes it absolutely
useless for anyone working for more serious enterprise organizations.
(And I fucking *refuse* to use Putty unless forced.)

**Run "docker" as god intended** from within a virtual Linux machine.
That's right, I'll be installing docker from the Linux command line into
my Kali virtual machine. No fucking Docker/Rancher Desktop to fight
with (both of which require WSL2 for optimization).

**I'll be using VMware Workstation Pro** since it is required by
OSCP certs. I will use Kali in VirtualBox for the Boost and as long as
the two VM applications are not running at the same time there
absolutely no problem (unlike the rest).

**I don't need long-term stability.** As ironic as it sounds, I don't
need my computer to be on all day. I can simply turn it on when I need
it for gaming or streaming, or leave it on and reboot is weekly or so.
This is because I'm no longer doing 24 hour streams with fish. If and
when I do something like that again, it will be from a dedicated systems
streaming to a specific, separate account.

**Windows dominates 3D (CAD, games).** This is no surprise. Microsoft
pioneered modern 3D desktop applications (DirectX). I don't do that much
gaming, but when I do I like having the option to play games that just
don't work on Linux at all, or are a pain in the ass to setup. Also, I
would love to get into SolidWorks and Overwatch (Windows only) again.

**StreamLabs is the leading streaming application** despite it being
highly proprietary and ripping off OBS. I can still use vanilla OBS, but
having all the power of StreamLabs is a compelling for someone operating
at this level of streaming these days. They make a very good product.

**Streaming game development is easier from Windows** since Windows
dominates that realm. This includes GameMaker (for which I have about 20
licenses) and Phaser3D as well as Unreal Engine and Unity with C#. I'm
not into game development, but if I wanted to do a fun stream or two
covering that I would be more able to do it.

**I need to get good with Windows C++, Assembly, and PowerShell** if I
want to hack like the pros and start making that sweet pentesting money
(which I know I'm easily capable of once I have the tools).

**"Windows 10 is the only supported operating system for OSEE"** means
that this is *the* system required by the most elite hacking
certification possible from Offensive Security. Might as well get used
to using it now. Oh, and this certification requires owning VMware
Workstation Pro version 15 or higher (which I also have).

Related:

* Troubles with VirtualBox and the Windows Subsystem for Linux  
  <https://nicolaiarocci.com/troubles-with-virtualbox-and-the-windows-subsystem-for-linux/>

* EXP-401 and the OSEE Certification \| Offensive Security  
  <https://www.offensive-security.com/awe-osee/>
