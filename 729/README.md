# Switching from Linux to Windows for Streaming

I've been forced recently to reorganize all the computers I use for work
and play. Here are some surprising conclusions leading to the decision
to switch from Linux to Windows workstation (with no WSL) and full Kali
Linux virtual machine as my daily driver:

**Personally, I just need a Linux terminal** that's it. I don't give a
shit how I get it so long as it is responsive and I can put TMUX on it.

**WSL2 may have a ton of bugs, not work with Cisco Anyconnect, and lack
graphics support** but is clearly the way everything is going, even Vagrant
supports it by redirecting everything to the host Windows system so that
the VirtualBox and other providers just work.

**I'll be using VMware Workstation Pro** since it is required by the
OSCP certs. I will use Kali in VirtualBox and from WSL2 for the Boost.

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
