# Learn netplan for Linux Networking

I cannot believe how much easier network management has become for
modern Linux. So glad I'm working on this enterprise home lab to catch
up with all these great changes. Just after discovering the amazing
`nmcli` I realized that it isn't even needed on the base install of
Ubuntu Server (which makes me love Ubuntu even more than before,
compared to Red Hat).

```
    net2:
        dhcp4: true
        dhcp6: true
        match:
            macaddress: 52:54:00:12:34:07
        mtu: 9000
```

* Ubuntu Bionic: Netplan \| Ubuntu  
  <https://ubuntu.com/blog/ubuntu-bionic-netplan>

* netplan generate: \`gateway4\` has been deprecated, use default routes instead - Unix & Linux Stack Exchange  
  <https://unix.stackexchange.com/questions/681220/netplan-generate-gateway4-has-been-deprecated-use-default-routes-instead>
