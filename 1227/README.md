# K8SAPP Metadata

Having consistent metadata in each K8SAPP Git repo allows the consolidation of this data later into a master manifest used to regularly check for version updates and such.
Each Git repo should begin with a specific prefix following the K8SAPP convention
(preferably `k8sapp-`). Each K8SAPP repo should contain a `k8sapp.yaml`
containing the following metadata:

`longname` unique long name within the scope of a given Git repo collection or service that may contain qualifiers similar to container image references (ex: `rwxrob/jupyterhub`)

`shortname` for referencing easily within local contexts and corresponding to the git repo name after the prefix (`k8sapp-jhub` -> `jhub`)

`title` descriptive title of 70 Unicode characters or less for creating lists of K8SAPPs 

`version` semver of this K8SAPP, *not* it's origin, `git tag` also must be synced

`repo` Git-friendly reference to the required source Git repo (usually HTTP)

`maintainers` optional list of primary contacts with `name`, `email`, `url`, `slack`

*Why no summary or description?*

These should best be placed in the required README.md file within the required Git repo since CommonMark is much more expressive.

*Why no `kubeVersion`?*

The `kubeVersion` in Helm is disastrously broken to the point of being
dangerous. In addition, any indication of a K8SAPP being usable by
a specific version *or greater* is simply a lie since there is no way
to guarantee future compatibility.

Moreover, the Kubernetes version is but one consideration. Some K8SAPPs
may have dependencies on specific versions of other installed
applications.

This complexity is best communicated and managed in the README.md file
itself and should probably not be automated.

Related:

* [20211115160539](/20211115160539/) Kubernetes Applications (K8SAPP) Management Conventions
