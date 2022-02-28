# Use `ssh -R 2222:localhost:22 <remote>` for NAT VMs

Starting a harmless SSH tunnel is a simple fix to an annoying situation
when testing different machine combinations on a local system using
VMware or VirtualBox while your host VPN is still on connecting you to
work. In order for the VMs to see the internal network they must be
configured for NAT within the guest host with VPN enabled, but then your
VPN thinks they are foreign and blocks connecting to them in ways that
would work without the VPN active. The workaround involves hosting an
SSH server (or just "sharing" if on a Mac) on your guest host
(workstation) and then connecting to it using ssh with `-R` to open
a reverse proxy. Then, you just need to `ssh localhost -p 2222` to ssh
connect into your NATed "jump" machine with access to all the other VMs
also running locally within your virtualization software.

Keep in mind that nothing in this setup is a violation of any security
policy since it is all contained within your computer. In fact, this is
almost exactly what Vagrant does when you do `vagrant ssh` and it
connects to a local port to proxy access to the invidual machine. We are
just doing it explicitly.
