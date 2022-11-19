# Workstation Docker Images FTW!

I cannot express the amount of joy being able to `docker commit
<containername>` and have a full backup of my entire workstation working
environment. I mean, it saves *everything* as if I had just put my
computer to sleep. This means at anytime anything could go wrong with my
shitty company laptop and I'll never miss a beat. Just reinstall Docker
Desktop (with WSL2 only for speed) and run the last committed image that
I have saved. Most companies have some sort of network attached storage,
so that means just store the image there, reset the computer, and pull
the image down to spin it up.

Of course, all of this is only possible if you are a terminal user. If
you are dependent on a GUI for anything your screwed, but there are
other ways around that stuff. Besides, X is just another file (socket)
and you can always set that up for even graphic applications.

I think that Arch Linux users will be particularly found of this
approach. Because your container is running within Docker in WSL2 you
are safe to use it provided you aren't stupid and port forward and mount
things you shouldn't.

One caveat to all this: make sure you don't commit your work image to
your public Docker repo. That would not make people happy. Just remember
to *only* type `docker commit <name>` and nothing more and you'll be
fine. Just make sure you export and save that image somewhere safe for
when your computer does die.
