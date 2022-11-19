# Easiest Way to Change Container Host Name

There are a lot of bad solutions to renaming a host on the Internet. I
just stumbled into the easiest way of all. Just commit the image and run
the image with the `-h <name>` flag this time. That's it. This is the
same way that you add new bind-mounts and ports and stuff as well, when
you forgot to do that when you initial ran the image.

