# Restore hung Linux Mint Cinnamon desktop and mouse

This is why I have `ssh` setup to connect remotely from another laptop or something.

First, attempt to keep all the windows and apps running.

```sh
pkill -HUP -f "cinnamon --replace"
```

If this doesn't work, it means the window manager itself is probably hung and has to be restarted (which will kill all running applications using the window manager).

```sh
sudo service lightdm restart
```

Alternatives include `mdm` and `gdm` depending on configuration, but for latest Ubuntu Linux Mint Cinnamon this works given you the displays as if the computer had been restarted.

