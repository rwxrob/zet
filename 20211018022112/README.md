# OpenShift Doesn't Even Use Go Templates

I don't have words for how fucking stupid the decision to not support Go
templates is in the OpenShift world. I will *never* willingly work with
OpenShift after learning about this (and a ton of other architectural
design fails):

> OpenShift Container Platform provides a number of default Instant App
> and Quickstart templates to make it easy to quickly get started
> creating a new application for different languages. Templates are
> provided for Rails (Ruby), Django (Python), Node.js, CakePHP (PHP),
> and Dancer (Perl). Your cluster administrator should have created
> these templates in the default, global openshift project so you have
> access to them.

First, why are they supporting so many templates? Pick one. This is just
going to make code bases completely unintelligible.

Second, there's no Go template here even though the `kubeadm`,
`kubectl` (and pretty much every other fucking utility related to
Kubernetes) has a `-o go-template` option *hard coded into it*. Why
would you be so stupid to not include them given this fact?

Tags:

    #k8s #cloud #redhat #rant #templates
