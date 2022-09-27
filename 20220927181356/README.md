# Disable IPV6 on Specific Linux Machine

There are so many problems with my favorite applications when they try
to use IPV6. They include `lynx`, `w3m`, even Kubernetes itself.

```
sudo sysctl net.ipv6.conf.all.disable_ipv6=1
```

By the way, here's what an `strace` of a hung application looks like
when it cannot handle IPV6.

Apparently, this is a standard part of hardening (in 2022), ironically.

This can all be done by not allowing DHCP6 in the network as well.
