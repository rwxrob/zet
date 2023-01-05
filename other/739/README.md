# Keep SSH from Timing Out and Disconnecting

Getting back into the enterprise has reminded me of all the little
quirks I used to have solutions for that I never had to deal with once I
ran my own show. One of them is keeping my Secure Shell connection from
timing out while in another pane or not looking at the computer
terminal. Adding the following to `~/.ssh/config` usually does the
trick:

```ssh
Host login
  HostName foo
  ServerAliveInterval 30
  ServerAliveCountMax 2
```
