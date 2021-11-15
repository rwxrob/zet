# Kubernetes *Real* Application Practices (KRAP)

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

Note that *none* of these methods includes any OPA Gatekeeper policy
validation, which is left up to you, the admin, to ensure it happens.
Helm charts frequently have flaws (ex: not allowing change of image tags)
and must be reviewed by any administrator not wanting a very unpleasant
surprise. 

The need for these applications is indeed very real, as is the implied
requirement of every admin to ensure the "extra stuff" gets done even
though the installation method does never help you to do so. It would
seem these projects and vendors don't care as much about such things,
they just want to get their software into your precious cluster.

KRAP is here to protect you from this crap by suggesting a common set of
best practices for dealing with each application where things could
easily go wrong without the proper attention they require. After all,
all of this stuff is being regularly updated by their creators and you
will be called upon to make those updates quickly, consistently, and
safely. Ultimately, *you* are responsible for their KRAP.

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

## KRAP Conventional Contract / Interface

* I agree to provide a git repo for each app (allows GitOps, etc.)
* I agree to provide a detailed README.md
* I agree to document or implement the following operations:
    * Check - version, dependencies
    * Fetch - acquire from external authoritative source
    * Validate - read Helm charts, OPA policy checks, infrastructure deps, etc.
    * Install - `helm install`, `kubectl apply`, etc.
    * Upgrade - `helm upgrade`, etc.
    * Uninstall - `helm uninstall`, etc.

These operations can be fulfilled simply by describing the methods to
accomplishing each operation in a `README.md`. Alternatively,
a light-weight executable (preferably a bash script with a common name,
like `krap`) can fulfill these operations with actual coded methods
(functions), for example:

```bash
krap check
krap fetch
krap validate
krap install
krap upgrade
krap uninstall
```

> ⚠️
> Do not allow any other arguments to be passed.

When using a script, it should *never* take any other arguments than the
main operations names since the goal is simplicity and specificity.
Reading through the executable code should tell anyone everything they
need to know --- in detail --- in order to fulfill these Kubernetes
application administrative operations. Such scripts should depend on the
`kubectl config` context rather than taking an argument or environment
variable.

## Vendoring

Vendoring is the process of saving external dependencies with one's own
code. KRAP leverages the vendoring approach to preserve Helm charts and
other YAML resource files that originate outside of the project.
Acquiring these external resources can be included in a `fetch` action
or simply documented in the README.md when an Internet connection cannot
be assumed.

Tags:

    #k8s #cloudnative #cloud #devops #krap
