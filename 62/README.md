# Keep Your Remove SSH Connection Active and Awake

Ever had your ssh connection drop from a timeout? Yeah, it's fucking
annoying. Add the following to your `~/.ssh/config` `Host` entry to fix
it:

```ssh
  ServerAliveInterval 30
  ServerAliveCountMax 2
```
