# Things Local VM Can Do That WSL2 Cannot

* Directly mount any block storage device
* Perform consistently without lag during sessions
* Install Docker without complications (no Docker Desktop needed)
* Take snapshots and share images with others
* Cannot disable and pause freeing resources (WSL2 is always on)
* Take reliable backups (although WSL2 does have `wsl --export`)
* Use Cisco Anyconnect VPN (WSL2 has 4-year old bug open)
* Can restart host and restart VM without restarting it as well
* Start multiple VMs and create miniature local clouds (`fluff`)
* Allow training, use, and creation of `systemctl` commands
* Not fuck up your git commits

Related:

* [20220219192411](/20220219192411/) Warning: WSL2 Fucks Up Git Repos
* <https://stephenreescarter.net/automatic-backups-for-wsl2/>
 
    #windows #wsl2 #linux #devops #virtualbox
