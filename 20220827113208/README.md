# Use nmcli to Manage Network on Modern Linux

One of the things I need to catch up on is use of `nmcli` to manage
everything about the network interfaces on Linux machines. All the old
`ifconfig` stuff is really old.

Note that this does not come by default on Ubuntu Server so will have to
be installed and activated:

```
sudo apt install -y network-manager
```

> This is because since Ubuntu 18.04, the network configuration file has
> changed from interfaces to netplan, and you need to use apt install
> network-manager again modify /etc/netplan/00-installer-config.yamllike
> this:
>
>   network:
>       renderer: NetworkManager
>
> This allows the network configuration to point to
> NetworkManager,then >   use netplan apply load this file. you can
> use nmcli device status check if the configuration is in effect
 

* Why is nmcli not configuring device? - Ask Ubuntu  
  <https://askubuntu.com/questions/1190504/why-is-nmcli-not-configuring-device>
