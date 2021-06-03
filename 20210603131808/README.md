# Is Kubernetes Good or Bad?

There is a substantial amount of respectful debate over whether
Kubernetes is actually an overly complex disaster or the new normal for
enterprise IT. While I was writing this, @cronoluminaire (from the live
stream) said, "It's obviously both." I tend to agree. 

*More of the debate can be read in my Discord channel under the
`#container` channel or at <https://twitch.tv/rwxrob>*

Some people who are responsible for large scale deployments in their
organizations are discussing doing everything the "old" way but with
virtual machines in their clouds rather than Kubernetes. 

There's no doubt that Kubernetes is about as complex as understanding an
entire operating system --- particularly when you include all the "third
party" stuff that is akin to device drivers in the Linux kernel world
(very roughly metaphorically speaking). "Kubernetes is the new OS" one
blog proclaimed in 2020. Perhaps that comparison is more apt than some
would notice on the surface.

Part of the debate hinges on alternative approaches at a higher level.
Some don't like containers. These people are all about Virtual Machines.
Their IT designs are based on providing essentially a Digital Ocean to
their people and letting them do whatever they want with the systems.
These people push for `ssh` connections into virtual machines and all
the other stuff falls into traditional IT management. This means there
has to be a patching strategy, etc. This is definitely less complex, at
first. But as soon as someone decides to run their own Kubernetes on one
of those hosts you have a problem, now you have four of them, all
managed by different groups. You gave up control for a reason, but now
you might be regretting it. There is no logical central system into
which everything must go, no centralized IT policies that can actually
be enforced, just a bunch of virtual systems with an interface of some
kind that manages them externally. This is the type of architecture for
which I created a number of audit compliance checking tools for IBM
Global Services, to audit all these systems and report them so IT
managers could fight with them about their lack of "compliance."

Others would like containers do the same thing as virtual machines
(essentially) but host them in more flat systems that don't attempt to
manage (some say "orchestrate") them in any way. Where I currently work
this is where the largest percentage of computing power is allocated
(and it is a lot, fifth largest HPC in the world, unofficially since not
reported). This provides the federated flexibility (which
manage updates much better than virtual machines) without the
centralization dependency and head-ache of an "orchestrator". It still
leaves a lot of policy problems though. What is to stop people from
firing up essentially a full 80GiB container (the size of Domino), or
two dozen of them all doing essentially the same thing but existing
mostly because of company politics and internal competition.

Then, of course, you have Kubernetes and its ilk. They force everything
to be a container and logically contain within themselves a large composite
monolith, one system to rule them all, the "master control program" of
our time. In fact, Kubernetes as a "control plane" where everything
that rules the kingdom of federated containers has a cushy palace. Here
these rulers will into life and death the container subjects. They
interpret the policy law of the land provided by their human overlords.
Some call this "orchestration" but it is really "tyrannical control". In
fact, the original name of Kubernetes is *still* BORG at Google (who
recently announced moving off of BORG and onto Kubernetes in order to
avoid "maintaining two code bases"). No wonder people who love control
and to chase the unicorns (\**cough*\* IT business people /
pointy-haired bosses) think Kubernetes is so great. And don't
misunderstand, it *is* great, but it has definite drawbacks. All that
control means you can *usually* manage things more easily (like that
part of Civ when you play a tyrant and things to be going very
well indeed, so efficiently). But a lot of this control is an illusion,
and centralization can come with a very high price in loss of security.
More on that later.

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
