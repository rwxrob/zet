# Last Wins in `/etc/sudoers`

Although it should be obvious, the last entries in the `/etc/sudoers`
file override whatever comes before. This means that if you are simply
trying to give yourself no-password-hassle `sudo` access you better be
sure to put the following line *after* any `%admin` or anything that
might override it.

```sudoers
%sudo   ALL=(ALL:ALL) ALL
...
rwxrob  ALL=(ALL:ALL) NOPASSWD: ALL
```
