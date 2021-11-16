# Helm All the Things

God knows I complain a lot about Helm, but I'm just now realizing it is
the best we have --- especially since discovering Helm plugins.

Plugins are a huge game changer. Rather than embed `helm` calls in a
home-grown application that has to be learned by everyone, plugins allow
`helm` to be the common user interface that can be extended as the
organization needs with specific plugins for validation and more. Even
the extension documentation takes the same form. And since plugins can
be written in *any* language everyone is more likely to be happy.

After a week of struggling with KRAP I've arrived at the conclusion that
the single best way for an air-gapped organization to consistently
manage its Kubernetes applications is to ensure that every single person
uses Helm for installation and administration including the use of one
or more Helm plugins to cover specific validation (can you say OPA
Gatekeeper) and other custom needs that do not fall within Helm's normal
functionality. This provides a powerful, consistent interface for all to
use when creating and maintaining even the most highly customized
application deployments.

This practice is already the norm for many large organization including
one *very* large, "air-gapped", investment bank according to one
community member where they also include image scanning for
vulnerabilities in their process.

By the way, the Operator Framework is a disastrous, irreparable failure.
OLM with full cluster-admin privileges is just Helm 2 Tiller all over
again, but worse. Not only does OLM require enterprise root (my term for
cluster-admin to your entire fucking cluster) but it also *requires*
access to the Internet to pull operators from their hub to
then be run as root. You can forget about being "air gapped" at all.
You would think all the shit RedHat spews about Docker and running as
root someone would have said something before this monstrosity was ever
released. No one should *ever* consider using the Operator Framework,
period. In fact, my confidence in RedHat in the cloud-native space is
now at an all-time low after discovering this. This is just fucking
idiotic architecture. They've had a ticket open for more than a year
pointing out this massive security risk and the responses are downright
juvenile.

And as for Kustomize? It simply does not have enough flexibility nor
support for templates to maintain a consistent interface for even the
most complex of applications. Some organizations flatten their Helm
applications into shell scripts with Kustomize. But at some point you
have to change a value in a file, and not just by adding yet another
overlay. I appreciate the annoyance of templates for everything since
they are so horribly abused, but at least you have them. Kustomize takes
too strong an opinion on this point hobbling this approach entirely. You
end up with a random shell script that everyone has to learn for each
and every application. Without consistent, strong conventions and
practices you get a heterogeneous collection of apps that have no
consistency whatsoever.

This all leaves Helm in the lead position despite its quirks, which is
probably why Helm is the only Cloud Native project with "mature" status
and also why it was officially added to the CKAD certification
requirements.

Related:

* [20211115160539](/20211115160539/) Kubernetes *Real* Application Practices (KRAP)

Tags:

    #k8s #helm #apps #cka
