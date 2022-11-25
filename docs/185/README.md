# Identify and Remediate Rather Than Gatekeep

Recently, I abandoned a mini-project and proposal for a `validate` Helm
plugin that used OPA Gatekeeper to pro-actively check a chart to see
that its configuration passed policies. Then I realized this would need
to be maintained in addition to the OPA Gatekeeper configuration itself.
I realized this is redundant and unnecessary but also not even optimal.
In fact, other more experienced community members questioned my
gate-keeping approach suggest an alternative focus on regularly and
automatically auditing what is currently in the cluster.

It's rather easy to get something past the gates and into your cluster.
It is more important to focus on identifying problems and risks in your
active cluster dynamically. This is what the Falco project aims to do. I
like the emphasis on adaptability which allows dynamic auditing to
adjust parameters much like machine learning security scanning software
in other realms of the industry. Eventually, we'll have bots patrolling
our Kubernetes clusters just like they do everything else. This is really
where I want to focus our attention rather than on dated gate-keeping
approaches.

Related:

* <https://falco.org>

Tags:

    #k8s #cloud #security #secops
