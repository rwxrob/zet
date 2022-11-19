# The `netcat`/`nc` Tools are BSD

Today I realized that the famous `netcat`/`nc` tools are a part of BSD
UNIX and have just been ported to Linux this whole time.

```
$ ls -l `which nc`
... /usr/bin/nc -> /etc/alternatives/nc
$ ls -l /etc/alternatives/nc
... /etc/alternatives/nc -> /bin/nc.openbsd
$ dpkg -S /bin/nc.openbsd
netcat-openbsd: /bin/nc.openbsd
```
