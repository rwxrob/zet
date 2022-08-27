# Goodbye Proxmox, Only 32 Nodes in a Cluster

For many (like me) Proxmox is just the wrong pick. I have 19 Mac
Minis, 30 Raspberry Pis, a 28 core server, old Mac Pro, six MSI
Tridents, and dozens of other computers. I ran into very odd behavior in
Proxmox as my cluster got to 14 in the cluster, stuff that made reboot
or try weird restarts of corosync. Eventually, the main web UI just
stopped being served all together, with zero explanation of why.
When I started reading that the official max for any cluster is 32. Then
I read about a lot of people having the same problems (or worse) with
Proxmox limitations, some of them even lost their VMs entirely. It
wasn't hard to decide to go with a raw Linux instead after that. I lost
a lot of time doing all those Proxmox node installs, but it was time
well spend to come to this conclusion for myself. Add Proxmox to the
list of things uninformed Linux people will blindly recommend without
asking what it is that you are trying to accomplish. I would *never*
suggest any business ever use it, like ever. It is an incredibly
architecture and frankly the decision to use corosync was a
disastrously bad one. Keep in mind that the entire purpose of the whole
thing is HA, backups, and availability. But all of this is better
accomplished by Kubernetes and just plain 'ol KVM instead. Certain
people in my community where telling me this, and they were right.
