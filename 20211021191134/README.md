# Podman Actually Is Objectively Superior to Docker

Installing `systemd` in containers running with `podman` is drop-dead
simple. Just install `podman`. Alias `docker` to `podman` if you want.
Pull down and run the `ubuntu` image and just `apt install systemd` and
you are good to go. Try that with `docker` and have fun mopping up all
the barf it spews from all the failures. 

This is because `podman` integrally depends on `systemd` and promotes
its use in everything. It doesn't force itself into your containers
bloating them, but it makes it as easy as `apt install systemd` to bloat
them out if you want to, and you actually probably will want to at some
point.

Say, for example, you are setting up a simulated network for training or
hacking. Normally, you would never install `openssh-server` but in order
to simulate or test something that does it might be useful. Installing
`sshd` on the base Ubuntu image is nearly impossible without `systemd`
and even if you did it, all the commands committed to memory related to
starting and stopping `sshd` would be completely wrong compared to an
actual machine. There are many other examples where installing `systemd`
is an absolute requirement.

This realization that `podman` destroys `docker` is a good example of
how my noob-ness with regard to containers and Kubernetes really will
show. To my credit, I only shared my initial impressions before saying
that I would likely have more context later. Well I have that context
now. 

Once upon a time I was a big Docker fan and was like "who cares about
the socket and daemon, I can mount it for docker in docker?" But I
overwhelmingly realize the major error of my ways now.

Love it or hate it, systemd is the standard on all enterprise host Linux
distributions, notably, RedHat (obviously), Suse (which is where the
`apt` package keys are), and (yes even) Ubuntu. You can complain about
how horrible systemd is, how much it doesn't follow the UNIX philosophy,
how much of a pain in the ass it is to even install in a container
because of all the `cgroups` mounting and crap, but, in the end, it just
does not matter. I hate to break it to y'all, but systemd has fucking
won. Get over it and accept it. (I know. I *hate* that this is true.) If
you want to work with container and cloud-native *at all* you have to
accept systemd in most host OSes on which your Nodes will run (for now,
God bless Sidero/Talos to deliver us from this evil by granting us K8S
on metal).

And besides, even if K8S on metal removes the requirement for systemd
eventually, we will still benefit from a systemd-aware container engine
because everyone knows that host and workspace containers, the magical
alternatives to full hypervisor VMs, are still *very* valuable. I am
realizing this even more now that both Minikube and Kind use the local
container engine to emulate hosts to provide a single-node cluster for
localized development and experimentation. These use cases make
installing `podman` a no-brainer decision.

Related:

* How to use Podman inside of a container  
  <https://www.redhat.com/sysadmin/podman-inside-container#main-content>

Tags:

    #podman #docker #systemd #containers
