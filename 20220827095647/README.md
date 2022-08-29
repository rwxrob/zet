# Goodbye Proxmox, Only 32 Nodes in a Cluster

For many (like me) Proxmox is just the wrong pick --- especially for a
home lab made up of lots of old PCs lying around. I have 19 Mac Minis,
30 Raspberry Pis, a 28 core HP Z640 server, one old Mac Pro, six MSI
Tridents, and dozens of other various computers.

I ran into very odd behavior from Proxmox as my cluster got to 14 in the
cluster, stuff that required me to reboot or try weird restarts of
corosync (no, restarting PVE services didn't work, and hasn't for many
others as well).

Eventually, it got so bad the main web UI just stopped being served all
together, with zero explanation of why. And, by the way, why the fuck is
Proxmox adding the complexity of a real-time web server to the mix? It
makes no sense at all --- especially considering that tools like libvirt
and virt-manager use GUI application frameworks instead. It might have
seemed like a good idea, but after reading the 10th complaint about
browsers screwing up status by not refreshing their up icons from red to
green I had to wonder who the dumb ass was that made that decision. The
last thing I want in a highly critical full-systems status and
monitoring dashboard is web caching bugs.

Then, I started reading that the official max for any cluster is 32.
Again, more people having the same problems (or worse) with Proxmox
limitations, some of them even lost their VMs entirely.

It wasn't hard to decide to drop Proxmox entirely after that and go with
raw Linux instead. I installed Ubuntu Server on everything (after
fighting with really bad Red Hat "we don't support Mac hardware"
problems that reminded me to never use anti-FOSS, enterprise cock
sucking, hypocritical, 2003-dishonestly-claiming-linux-community-support
Red Hat for anything ever again).

I lost a lot of time doing all those Proxmox node installs, but it was
time well spend to come to this conclusion for myself, even if Ubuntu
Server installs much more quickly than even Proxmox (and can be
automated), which surprised me.

Add Proxmox to the list of things some Linux people will blindly
recommend without asking what it is that you are trying to accomplish.

I would *never* suggest any business ever use Proxmox, ever, no matter
what the size and how many Linux, over-engineering zealots will cry
about it. It just does not have the true high availability and
sustainability that they promise. In fact, when you ask most Proxmox
fans how many nodes they have, the answer is almost always under 10,
which isn't enterprise scale at any level.

Proxmox is an incredibly bad architecture and frankly the decision to
use corosync was horrible. Keep in mind that the entire purpose of the
whole thing is HA, backups, and availability. But all of this is better
accomplished by Kubernetes and just plain 'ol KVM instead. Certain
people were warning me about this from my community, and they were
right. Unfortunately, I need to see things for myself to understand why.
I get it now.
