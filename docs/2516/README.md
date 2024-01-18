# Fix connection from laptop to VM after sleep

By going into VMware Virtual Machine -> Network Adapter -> Network Adapter Settings and toggling off and on the Connect Network Adapter check box you can monitor the change or refreshed IP live while watching the summary view of the running VM. Using `ssh` into that IP will then work (where it didn't before). This works even when the network adapter is running under NAT because the terminal running on the host and the VM are still on the same internally routed network.
