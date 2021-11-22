# Kubernetes Applications (K8SAPP) Management Conventions

There are many ways to install and manage Kubernetes applications:

* `kubectl` Scripts
* Kustomize
* Helm
* Modified Helm
* Operator Framework
* Custom Operators
* Adapted Terraform and/or Ansible

Cloud native administrators are forced to learn one or all of these
since there is no agreement in the industry as to a standard. Moreover,
the industry is full of overly-hyped frameworks and "package managemers"
vying for dominance while failing to meet even minimal requirements for
air-gapped security and sustainability. This situation, brought
about by attempting to force imperative IT business processes into
declarative "solutions," has created chaos and a climate of conflict and
shame for those refusing to use the Kubernetes application management
"standards" when, in fact, the safest and most sustainable approach is
to keep things simple: just use Kubernetes resource files and `kubectl` and
follow a conventional methodology.

Amidst the chaos, a common set of admin practices seems mandatory so
that each application is looked after in a way that is implementation
agnostic (like you would do with an interface when programming). One
does not care *how* these practices are fulfilled, only that they are.
Some can be scripted, some are a matter of documentation, but all are
required for any application to makes it into your production cluster.
One could say that every application can implement its own *methods* for
the same *operations*. Operations are the actions taken by any cloud
native admin, or by a script on behalf of the admin. 

To be clear, this is not yet-another-abstraction (even though it can be
implemented as such). It's just a matter of agreeing on what everyone on
the admin team should do with respect to *all* Kubernetes applications
while allowing each its own specificity.

The K8SAPP contract states:

* I agree to provide a git repo for each app (allows GitOps, etc.)
  * Name repos with consistent prefix (ex: `k8sapp-myapp`)
* I agree to provide a detailed README.md
* I agree to keep a vendored copy of the original application
* I agree to document the following procedures (as `##` in README.md):
    * Fetch - acquire from external authoritative source
    * Validate - GPG, read Helm charts, policies, infrastructure deps, etc.
    * Configure - adapt original to match environment (`values.yaml`)
    * Install - `helm install`, `kubectl apply`, etc.
    * Upgrade - `helm upgrade`, etc.
    * Uninstall - `helm uninstall`, etc.
    * Check - version, dependencies, is there an update?
* I agree to add a *## Related* section with related reading when
  available

> 💡
> Consider creating a `template-k8sapp` for your organization in your
> Enterprise GitHub so that people can simply clone/copy it and fill it
> in. This takes a lot of the busy administrative work out of the
> process.

Vendoring is the process of saving external dependencies with one's own
code. K8SAPP leverages the vendoring approach to preserve Helm charts and
other YAML resource files that originate outside of the project.
Acquiring these external resources can be included in a `fetch` action
or simply documented in the README.md when an Internet connection cannot
be assumed.

Related:

* [20211122163452](/20211122163452/) "Package Management" Will Never Work in Kubernetes

Tags:

    #k8s #cloudnative #cloud #devops #k8sapp
