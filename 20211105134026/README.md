# Disaster (Moving to Windows) Averted

All this IRL streaming stuff (driven by desire to share machine builds,
networking, running, long-boarding, reading a good book, camping,
interviewing interesting people, capturing art shows, and making coffee
on stream) warped my brain into thinking that I *had* to use StreamLabs
OBS to really be a serious streamer. Also, OBS continues to crash or
require a reboot when making a new RTMP Media Source. But the change was
mostly prompted by the fact that StreamLabs has a fully synchronized
interface across *all* devices, including mobile, which is what I was
exploring. The SL mobile app is really the only significant offering in
the space. It allows (almost like a Linux app) customization of
*everything* and allows multiple streaming to different targets as well
as local LAN. Let's just say that the GoPro app does *not* allow that.

Having a powerful, portable live-streaming "lab" on your mobile device
is really a must for IRL streaming. It allows setting up interviews and
putting your "camera" on a tripod and all the normal things you would
require a camera specialist to focus. Plus, if I am doing anything where
I move intensely it is the *only* way to add a camera with motion
stability (like GoPro or Sony). The SL app is pretty much exactly what I
would create if I wanted an app on my phone.

Thankfully JalopyJones and others reminded me that creating a rig with
just a 4/5G router is just a matter of adding a webcam to a Rasperry Pi
(or equivalent). The rest is just the same as any local LAN setup. (I'll
write about that separately.) During the conversation, however, the most
important realization hit me. 

**What do I do on the road if my OBS on my home/cloud server needs
restarting?**

This one reality check was all I needed so say me from realizing that
Windows is *never* the answer for this kind of stuff. After all, most of
the devices that are front-and-center in the competition for
live-streamers dollars are built on Linux internally (LiveU, x.265
encoder, etc.). Windows is trying its hardest to become Linux and Mac
has been UNIX based for the last two decades or so. UNIX/Linux has won,
so why would I invest time in learning something else?

Plus when something goes wrong in Linux (as does happen) I can actually
do something about it to fix it. Most of the time this is completely
impossible in Mac or Windows. There are FOSS offerings, but they are
usually shrouded. I really like that SL OBS is fundamentally built on a
FOSS application (OBS) and their plugins are available for those who
want to use their own OBS. It is true, however, that the Linux OBS is
woefully behind the OBS Studio applications for Mac and Windows. But,
for me, that's not complete a problem. 

What *is* a problem is OBS Media Sources hanging when the RTMP/SRT
stream stops. I have to cobble together something to watch for and
correct that or even find or write my own plugin to manage it. Such
a task would be virtually impossible on Windows (but not completely
because, after all, it is also just OBS). Worst case, I could ssh into
my home OBS system and correct the problem remotely. The idea of
attempting the same on Windows is terrifying.

Then there is the whole issue of uptime. I've never had a Windows system
stay up more than a few days. Inevitably, something breaks. But my Linux
workstations regularly go a month or more without a reboot. This is
because of the fundamental flaw in Windows OS design that ties the
desktop (windows) code to the OS itself. The UNIX philosophy is what
keeps Linux so robust and sustainable despite the frequent quirks. It is
*very* rare for a Linux application to force the entire OS to be
rebooted. So even if OBS hangs or crashes, the supporting OS to which I
would need to ssh into from the road, is rock solid and really unlikely
to require a reboot ever. This is a serious fucking consideration for
people managing their own OBS workstations for their streaming (which
greatly reduces the cost because there are no cloud fees involved). In
fact, it's really the only viable way to do any serious IRL streaming
from the road in a digital nomad style.

> 💬I wish they would make an OBS that you can run headless from the
> cloud, but that's unlikely. It would still be expensive, however, to
> send a 1080p stream to (and from) it constantly.

So I'll be staying on PopOS even though I really detest the changes they
made to the window manager that force you to pick between zooming in and
out on all windows or searching for an app. These were combined before
and have been broken out. That was a *huge* design mistake made by
people who don't use it.

Tags:

    #lessonslearned #tips #irl #windows #linux
