# Hold Up: Minikube Requires "Driver", Go VirtualBox

In my exploration of Minikube as a better beginner starting point I just
realized (while testing on a fresh Windows install here at home) that I
completely missed the "driver" requirement (duh). Here are the drivers
supported on a Windows machine:

* `docker`
* `hyperv`
* `vmware`
* `virtualbox`

This means one of these things has to be installed before `minikube
start` will even work.

So which is the easiest?

I hate saying this: they are all equally annoying.

With `docker` you have to install Docker Desktop, unless you go through
the decidedly painful process of using some other way to get a `docker`
command installed. And, by the way, if you are going to just install
*into* a Docker engine you might as well just use `kind`, which seems
far easier.

As for `hyperv`, most will say, "What the fuck is a `hyperv`?" There's
nothing wrong with looking it up. It is just a virtualization layer
between your hardware and host operating system and *other* operating
systems. (Search for illustrations.) These days you cannot even get a
hypervisor without "enabling it in your BIOS" which is the polar
opposite of "simple" for most beginners. Some will discover their older
hardware doesn't even support it (mine didn't). And once you have
enabled in the BIOS you must still install one.

On Windows these days the most direct way to get a `hyperv` driver
installed is to install WSL2, which enables the use of a full Linux
terminal all by itself. WSL2 is pretty standard these days, even in the
enterprise, but still suffers from major problems with OpenConnect VPN
connections that make it a pain in the butt requiring customized shell
scripts to get it to work with a VPN. 

> 💬
> By the way, the difference between WSL 1 and 2 is that 2 is a true
> hypervisor and 1 is an emulator. Neither is super easy for an
> absolute beginner to grok.

The `vmware` option is the first *virtual machine* option. It
effectively requires you to buy VMWare. Technically, that's not
completely true. You probably want to skip this and use the next
"virtual machine" option. Most do.

The `virtualbox` option requires you to install Oracle's VirtualBox.
Don't worry, Oracle didn't invent it (thank God). They bought out the
company and have made it free for everyone for some time. It's inferior
to VMWare (I paid for VMWare Pro) but it's definitely good enough. All
you have to do with this option is download the installer and run it,
accepting 'Run as Admin' as you do. It is by far the simplest solution
to the must-have-driver `minikube` requirement. Plus you get the added
bonus of being able to use it later to install any number of operating
systems and try them out before you 'buy' them and install to your
actual hardware. Wanna compare Arch versus PopOS? VirtualBox has got
you. I had `minikube start` working within four minutes after installing
VirtualBox and just accepting all the defaults, clicking through
everything with wild abandon.

The `virtualbox` driver also has the added advantage of having
a consistent user interface across *all* operating systems. The other
options --- including the VMWare software --- all have noticeable
differences between their interfaces. As someone who sometimes must
address a heterogeneous group of people coming from all three OSes,
having this commonality is very convenient. Yes, even on Linux, since
you can run Windows there on occasion to try and hack/break it. You know
you will want to. In fact, you *must* do this to get the OSEE
certification while at DEFCON.

Everyone will have to 'choose their own adventure' here, but my clear
recommendation is to install VirtualBox because it will have so many
other practical applications later. Plus, it saves you from a dependency
on the proprietary Docker Desktop software.

    #minikube #k8s #linux #virtualbox #vm #cloud #docker
