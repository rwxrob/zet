# Just use kubeadm for Kubernetes installs

Even though the (horrible) official docs from Kubernetes web site say
you have the option of using `kubeadm`, `kops`, or `kubespray` you
really don't have those options when doing a secure, on-prem private
deployment.

The `kops` tool appears to be only for AWS.

The `kubespray` tool is definitely designed primarily for cloud provider
deployments and requires that "your firewall must be disabled" in order
for deployments to work when doing it on-prem, which is a non-starter,
obviously.

This leaves `kubeadm` as the only true option for people who actually
care about their internal infrastructure of an on-prem deployment.

I must say, the more I get into Kubernetes the more disappointed I am in
the base technical ability and IT acumen of those involved. This shit is
just stupid dumb, and I'm not even talking about the partial sentences,
lack of basic grammar, and punctuation in the documentation. I don't
know whether I should run screaming or embrace it and work to improve
it with community contributions. Don't get mad, Rob, get busy.
