# Dropping `microk8s` from Learning

After talking with a very experienced Kubernetes pro I've decided to
save time and cognitive overhead and not learn `microk8s` at all. The
reason is because that is learning time better allocated to learning
*real* Kubernetes and some sort of deployment method including Ansible
or Terraform, even locally on hardware. When doing applications
development there simply is nothing better than `kind`, which
specifically targets that use case. At the end of the day, `microk8s` is
not intended to be used as a training or personal lab for Kubernetes,
it's meant to, um, be a micro-scaled version and therefore has some very
fundamental differences internally that would be counter-productive for
someone seeking to support Kubernetes at large scale in any
organization, like me. I want as close to an exact replica or our
enterprise cloud architecture as possible so that I can test things
locally here (within reason). I'm actually really excited to get into
Ansible a bit more, perhaps I'll actually enjoy all the Python I have to
start using again to make it work. This decision has been validated
this week at work were Cisco ACI isn't playing nicely with MetalLB, you
know, the kind of stuff you would never be able to simulate at home, but
would at least have more work with. This also is an argument against
setting up a "home lab" in GCP or something, because you miss out on all
the hardware and network setup and practice.
