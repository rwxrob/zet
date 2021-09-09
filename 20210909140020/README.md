# Use `minikube` Instead of WSL2 and Docker Desktop

I've written how much I hated `minikube` before. I was just so wrong.
I didn't get it. Now I'm a bit dangerous with Kubernetes and understand
why `minikube` is absolute the best beginner choice, not only for people
wanting to learn Kubernetes and Cloud-Native, but anyone who wants
a Linux terminal with the least number of install steps.

I will *never* use WSL2 and Docker Desktop on Windows again and probably
stop using `kind` altogether as well despite the initial recommendations
of my professional friends. I must have different needs than them.

> 🤬
> I'm not mad at my friends who recommended `kind`. I'm mad that
> I didn't question their recommendations more directly myself.
> I encourage people to always make your own decisions and in the case
> of `kind` vs `minikube` I did not. I just did what they recommended.
> It's a reminder to *always* check anything anyone tells you, no matter
> how much authority and experience they have. This absolutely goes for
> anything I say as well (as this conclusion obviously demonstrates.)

What I didn't understand is that `minikube` comes with *everything* you
need for Mac, Windows, or Linux because it has its own *built-in*
virtual machine. Here are the steps to get a *full* Linux prompt on
*any* of these OSes:

1. Download and run the `minikube` installer
2. `minikube start`
3. `minikube ssh`

I have been evaluating time-to-local-linux-terminal approaches for more
than 15 years and that is by far the simplest I have ever encountered.
Of course, there are caveats, but there is simply no faster way to get
a beginner onto the Linux command line, period. Obviously, this is my
new number one recommendation for the Boost.

It gets better.

**Minikube includes a full FOSS-compliant Docker** (including the `docker`
command). That's right, it has *everything* Docker Desktop includes but
also allows you to swap out the container engine later to something else
if you don't want Docker (and many no longer do). And Minikube is 100%
open source under the CNCF Kubernetes umbrella, meaning it will never
surprise you with a proprietary fee someday.

**Minikube also has more options for mounting local directories** and
handling integrations with your local workstation that I completely
missed when I first looked at it. Honestly, I didn't understand
Kubernetes well enough to appreciate them.

**Minikube is a full Kubernetes control plain node** that just happens
to be a *virtual* machine instead of a real one. In almost every other
way it is exactly the same as installing all of Kubernetes on
a dedicated single computer. This means you aren't wasting any or your
learning on specific things that don't directly apply to what you will
eventually be doing on actual machines. No wonder this is the *official*
educational approach to Kubernetes. I'm really glad I finally realized
why (despite the advise of my professional friends).

**Minikube protects you from Docker safety issues.** Because the Docker
engine is embedded within a virtual machine if you accidentally pull
down and run a Docker hub image that contains malware you are more
protected than just having Docker installed by itself. I'm sure this is
the number one reason that CNCF got behind Minikube as the official
recommendation. It is also a main reason I'm using Minikube in the Boost
and not Docker Desktop. The Docker security thing has been an ongoing
thread in the Kubernetes vs Docker saga.

**Minikube works with OpenConnect VPN.** WSL2 does not. Sure you can write
a bunch of bash and PowerShell customizations to get around the known
bug when WSL2 and OpenConnect VPN are combined, but Minikube just works
because it uses a VM and virtual network that is contained within the
OpenConnect VPN network. It just works. Docker Desktop has the same
advantage, but Minikube fulfills that same need.

There are still a number of things I'm evaluating, such as using the
embedded docker engine as a private registry, but I'm almost sure that
those will work if I tag those images properly. I'll write that up
separately.

Related:

* [20210909142047](/20210909142047/) Surprise, Docker Desktop is Proprietary (Not FOSS)
* [20210901132113](/20210901132113/) Docker Desktop for Business No Longer Free
* [20210701203752](/20210701203752/) Fix WSL2 Cisco AnyConnect VPN Failures
* [20210505174709](/20210505174709/) Docker Desktop Uses Network and DNS from Host
* [20210505180154](/20210505180154/) Docker Desktop Kubernetes Single-Node Cluster
* [20210701190237](/20210701190237/) Windows Docker Desktop is Torture, Gimme Linux
* [20210702142020](/20210702142020/) Docker Desktop Fatal .NET Error

Tags:

    #k8s #cloud #minikube #docker #cncf #tips #tools
