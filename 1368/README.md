# I am Installing Talos OS (Sidero) at Home

After all that write up about using a "boring OS" for production
environment Kubernetes deployments I cannot stop looking at Talos OS
(now known as Sidero). I just cannot resist. They get so many things
right, (even something as trivial as having a Matrix server for chat in
addition to Slack).  They have *both* a RAM-disk image for booting and a
network boot image as well. That is something I've been wanting to setup
correctly for a long time. I just change the BIOS to network boot and
power on the machines to get the latest Talos OS image running. No need
to change anything else.

What really sealed my decision was reading all the support for multiple
GPUs that are built in. You have to wonder if all the team members are
using this for ML and crypto stuff, because it is pretty much completely
ready to setup to run a k8s cluster to do exactly those applications.

I get the distinct impression from reading the source threads and chat
and documentation that the creators of Talos were really internally and
personally motivated from the very beginning --- especially by the
strong desire to make a rock-solid secure operating system that is
virtually unhackable by its very implementation. You don't see *any* of
the other comparable, boring operating systems leading with the
following first paragraph:

> Why Talos?
> 
> Security
> 
> Talos reduces your attack surface by practicing the Principle of
> Least Privilege (PoLP) and by securing the API with mutual TLS
> (mTLS) authentication.

This was their number one raison d'etre. None of the others have cared
about this, which is why DefCon 2021 had several keynotes and sessions
focused on hacking Kubernetes. Talos addresses these in the most
comprehensive way possible.

In fact, the more I got to reading about the company, it's focus on
picking interesting names, and all the other core IT and design
decisions --- even their choice of the MPL-2 license --- the more I
sincerely found myself planning what I would have to do to make myself
an indispensable member of their engineering and development team. I
haven't felt that way about a company since studying Hashicorp. Who
knows, perhaps this little bare-metal passion project at home might take
me further down the road, say within the next five years. I love my job
now, but ultimately I will eventually be working for a company that
develops Linux systems software and utilities related to cloud and
Kubernetes. It's kind of my destiny.

Tags:

    #talos #sidero #linux #baremetal #secops
