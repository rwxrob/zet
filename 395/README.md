# Alternatives to OPA Gatekeeper, Kyverno?

Even if I never have any say in getting rid of OPA Gatekeeper at "work"
and even if everyone *must* learn OPA Gatekeeper to get CKS certified (I
just reconfirmed) I really want to understand which of these I want to
deploy to my home lab and get good at. Gatekeeper and Kyverno are the
leading policy engines right now. Gatekeeper is a fully matured CNCF
project, Kyverno is a "sandbox" project, but has been around for more
than a year at this point.

OPA Gatekeeper has some very serious warts and almost zero
documentation. The most annoying that we've hit lately is with the
selector operators that isolate the resources before passing them to the
Rego rules. The logic appears to be exactly the opposite of what is
documented and the source seems to confirm that it simply isn't doing
what it should.

Currently, there are few alternatives to OPA Gatekeeper. Kyverno is the
one that everyone raves about, but it's pseudo-code language is
absolutely ugly as sin, but if it works, it's no worse than reverse
logic in Gatekeeper and Rego. At least it is still YAML.

> Kyverno was written from the start solely for use in Kubernetes.

* OPA Gatekeeper in the Admission Controllers\' World :: Nuno Adrego  
  https://nunoadrego.com/posts/opa-gatekeeper-in-the-admission-controllers-world/

* Kubernetes Policy Comparison: OPA/Gatekeeper vs Kyverno \| Neon Mirrors  
  https://neonmirrors.net/post/2021-02/kubernetes-policy-comparison-opa-gatekeeper-vs-kyverno/

    #k8s #gatekeeper
