# Kubernetes *Real* Application Methodology (KRAM)

KRAM is a methodology for administering Kubernetes applications in the
real world.

Let's face it, there are far too many ways to install and manage
Kubernetes applications today. What's worse is that as a cloud-native
administrator you don't get to choose. This leaves you responsible to
maintain an extremely diverse set of applications. Here are just some of
the installation and management approaches used today:

* Shell (`kubectl apply`)
* Kustomize
* Helm
* Modified Helm
* Operator Framework
* Custom Operators
* Adapted Terraform or Ansible

Helm charts frequently have flaws (ex: not allowing change of image tags)
and must be reviewed by any administrator not wanting a very unpleasant
surprise. 

The need for these applications is indeed very real, as is the implied
requirement of every admin to ensure the "extra stuff" gets done even
though the installation method does never help you to do so. It would
seem these projects and vendors don't care as much about such things,
they just want to get their software into your precious cluster.

KRAM is here to protect you from this by suggesting a common set of best
practices for dealing with each application where things could easily go
wrong without the proper attention they require. After all, all of this
stuff is being regularly updated by their creators and you will be
called upon to "kram" those updates into your cluster quickly,
consistently, and safely.

A simple solution to this problem is to simply enforce a common set of
admin practices for each application in a way that is implementation
agnostic (like you would do with an interface when programming). You
don't care *how* these practices are fulfilled, only that they are. Some
can be scripted, some are simply a matter of documentation, but all are
required for *any* real application to makes it into your production
cluster. You could say that every application can implement its own
*methods* for the same *operations*. Operations are the actions taken by
any cloud-native admin, or by a script for the admin. 

To be clear, this is not yet-another-application-abstraction (even
though it can be implemented as such). It's just a matter of agreeing on
what everyone on the admin team should do with respect to *all* k8s
applications while allowing each its own specificity.

## KRAM Conventional Contract / Interface

* I agree to provide a git repo for each app (allows GitOps, etc.)
  * Name repos with consistent prefix (ex: `k8sapp-myapp`)
* I agree to provide a detailed README.md
* I agree to document the following procedures:
    * Get - acquire from external authoritative source
    * Validate - GPG, read Helm charts, policies, infrastructure deps, etc.
    * Configure - adapt original to match environment (`values.yaml`)
    * Install - `helm install`, `kubectl apply`, etc.
    * Upgrade - `helm upgrade`, etc.
    * Uninstall - `helm uninstall`, etc.
    * Check - version, dependencies, is there an update?

## Vendoring

Vendoring is the process of saving external dependencies with one's own
code. KRAM leverages the vendoring approach to preserve Helm charts and
other YAML resource files that originate outside of the project.
Acquiring these external resources can be included in a `fetch` action
or simply documented in the README.md when an Internet connection cannot
be assumed.

Tags:

    #k8s #cloudnative #cloud #devops #kram
