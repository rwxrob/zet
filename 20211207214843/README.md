# Enabling Socks Proxy in APT Configuration

Add the following to an `/etx/apt.conf.d` file:

```
Acquire::http:Proxy "http://...";
Acquire::https:Proxy "http://...";
```

Don't forget the semicolons. Some VPNs will have the same URL for
both http and https.

Related:

* apt-get install via tunnel proxy but ssh only from client side  
  <https://stackoverflow.com/questions/36353955/apt-get-install-via-tunnel-proxy-but-ssh-only-from-client-side>

Tags:

    #apt #linux #tips #proxy #vpn
