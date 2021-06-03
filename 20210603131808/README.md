# Is Kubernetes Good or Bad?

There is a substantial amount of respectful debate over whether
Kubernetes is actually an overly complex disaster or the new normal for
enterprise IT. While I was writing this, @cronoluminaire (from the live
stream) said, "It's obviously both." I tend to agree. 

*More of the debate can be read in my Discord channel under the
`#container` channel or at <https://twitch.tv/rwxrob>*

Some people who are responsible for large scale deployments in their
organizations are discussing doing everything the "old" way but the
virtual machines in their clouds rather than Kubernetes. 

There's no doubt that Kubernetes is about as complex as understanding an
entire operating system --- particularly when you include all the "third
party" stuff that is akin to device drivers in the Linux kernel world
(very roughly metaphorically speaking). "Kubernetes is the new OS," one
blog proclaimed in 2020. Perhaps that comparison is more apt than some
would notice on the surface.

Part of the debate hinges on alternative approaches at a higher level,
some don't even like containers, they are all about Virtual Machines
instead. Their IT designs are based on providing essentially a Digital
Ocean to their people and let them do what they want with the systems.
These people push for `ssh` connections into virtual machines and all
the other stuff falls into traditional IT management. This means there
has to be a patching strategy, etc. This is definitely less complex.
There is no logical central system into which everything must go, just a
bunch of virtual systems with an interface of some kind that manages
them externally.

Others would like container do the same thing as virtual machines
(essentially) but host them in more flat systems that don't attempt to
manage (some say "orchestrate") them in any way. Where I work this is
where the largest percentage of computing power is allocated. It
provides the flexibility of containers (which manage updates much better
than virtual machines) without the centralization dependency and
head-ache of an "orchestrator". 

Then, of course, you have Kubernetes and its ilk. They force everything
to be a container and logically contained within a large composite
monolith, one system to rule them all, the "master control program" of our
time. In fact, they main containers are stored in the "control plane"
where everything that matters dominates the kingdom of federated
containers that it wills into life and death based on its interpretation
of its human overlords "policy" desires. Some call it "orchestration"
but it is really "tyrannical control". In fact, the original name of
Kubernetes is *still* BORG at Google (who recently announced moving off
of BORG and onto Kubernetes in order to avoid "maintaining two code
bases"). No wonder people who love control and to chase the unicorns
(\**cough*\* IT business people / pointy-haired bosses) think Kubernetes is
so great. And don't misunderstand, it *is* great, but it has definite
drawbacks.

As I continue to learn everything there is to know about k8s, I sincerely
feel like I'm learning all the inner workings of a rather strange OS
that uses gRPC instead of internal bus calls, that the debate over
monolith (Linux) and microkernel (HURD) has just shifted to a sort of
meta level. (We all know who won there.)

In a very subtle way the debate about `systemd` (which really isn't a
debate any more) is like arguing for cloud+VM versus
cloud-native+Kubernetes with Kubernetes being compared to the monolith
of `systemd` even though you have to go pretty high to see the system
from the trees (so to speak). Sure these things have very distinct
differences, but they feel similar based on design principles.

Google has proven over and over that it could give a shit about the UNIX
philosophy, that it is all about control, that its engineers are more
prone to add three layers of abstraction for no fucking reason, and so
far I'm seeing that a lot in the Kubernetes architecture. Even more
troubling, recently I learned that all the "Secrets" are stored in
`Etcd` as Base64 unencrypted strings (at least [by default]). That's
fucking moronic and *seriously* dangerous. If a hacker gets into the
control plane and accesses that DB they will have *all* the security
secrets for the entire fucking enterprise IT architecture. You don't
have to have an overpriced DevSecOps title to understand that. That
level of centralization is fucking dangerous and I suspect I'll keep
uncovering more.

[by default]: <https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/>

Perhaps I am still just new and I don't fully appreciate the
requirements for those abstractions, just like I could never be anywhere
near a kernel (or even device driver) developer, that this complexity is
essential and just beyond my appreciation at the moment. Or, it could
just all be bullshit.

I'm a simple, practical man. If Kubernetes doesn't get us closer to the
higher *actual* goal --- the immediate need --- not some anticipated,
maybe-could-one-day-need thing then I say, "fuck it." I don't care how
"mainstream" or "dominant" or "industry standard" it becomes. (We all
know that means nothing in the tech industry when something truly better
comes along. Remember Netscape? Didn't think so.) One way or another
Imma found out. I'll let you know.

What's an 'Ingress' again?
