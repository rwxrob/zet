# Hold Up: Minikube Requires "Driver", Go VirtualBox

In my exploration of Minikube and consideration as a better beginner
starting point (for most) I just realized (while testing on a fresh
Windows install here at home) that I completely missed the "driver"
requirement (duh). These are the drivers supported (on a Windows
machine):

* `docker`
* `hyperv`
* `vmware`
* `virtualbox`

This means one of these things has to be installed before `minikube
start` will even work.

So which is the easiest?

I hate saying this: they are all equally annoying.

With `docker` you have to install, um, Docker Desktop (unless you go
through the decidedly painful process of using some other way to get a
`docker` command) installed. And, by the way, if you are going to just
install *into* a Docker engine you might as well just use `kind` (which
seems far easier).

As for `hyperv`, most will say, "What the fuck is a `hyperv`?" There's
nothing wrong with looking it up, but it is just a virtualization later
between your hardware and host operating system. These days you cannot
even get one without "enabling it in your BIOS" which is the polar
opposite of "simple" for most beginners, if they even have support for
it. And once you have enabled in the BIOS you must still install one.

On Windows these days the most direct way to get a `hyperv` driver is to
install `wsl2`, which enables the use of a full Linux terminal all by
itself (that won't work with OpenConnect VPN without a custom script of
some kind). By the way, the difference between WSL 1 and 2 is that 2 is
a true hyper-visor and 1 is an emulator. Neither is super easy for an
absolute beginner to grok.

The `vmware` option effectively requires you to buy VMWare. (Technically,
that's not completely true.) But you probably want to skip this and use
the next "virtual machine" option.

The `virtualbox` option requires you to install Oracle's VirtualBox.
Don't worry, Oracle didn't invent it (thank God). They bought out the
company and have made it free for everyone for some time. It's inferior
to VMWare (I paid for Pro) but it's definitely good enough. All you have
to do with this option is download the installer and run it, accepting
'Run as Admin' as you do. It is by far the simplest solution to the
must-have-driver requirement. Plus you get the added bonus of being able
to use it later to install any number of operating systems and try them
out before you 'buy' them and install to your actual hardware. I had
`minikube start` working within four minutes for installing VirtualBox
and just accepting all the defaults, clicking through everything with
wild abandon.

Everyone will have to 'choose their own adventure' here, but my
recommendation is to install VirtualBox because it will have so many
other practical applications later. Plus, it saves you from a dependency
on the proprietary Docker Desktop software.

    #minikube #k8s #linux #virtualbox #vm #cloud #docker
