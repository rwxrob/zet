# Operator Lifecycle Manager (OLM)

> ⚠️
> The OLM approach to K8S software installation and management does not
> provide for organizations with "air gapped" policies and architecture.
> It simply does not work without Internet access to `operatorhub.io`.

> ⚠️
> Operator Lifecycle Manager (OLM) runs with cluster-admin privileges.
> ...
> Cluster administrators should take measures to ensure that an Operator
> cannot achieve cluster-scoped privileges.

This is a thing from RedHat that is taking the K8S world over. I think
it might be just a trend, but if so, at least it appears to be better
than Helm (as far as I can tell for now).

> ⚠️
> This is Tiller all over again. Do *not* use Operator Framework for
> anything until this massive security risk is addressed (which cannot
> be by the core design.

```yaml
# Source: original/0000_50_olm_01-olm-operator.serviceaccount.yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: system:controller:operator-lifecycle-manager
  labels:
    addonmanager.kubernetes.io/mode: Reconcile
rules:
- apiGroups: ["*"]
  resources: ["*"]
  verbs: ["*"]
- nonResourceURLs: ["*"]
  verbs: ["*"]
```

Related:

* Operator Lifecycle Manager  
  <https://olm.operatorframework.io/>
* <https://docs.openshift.com/container-platform/4.9/operators/admin/olm-creating-policy.html>
* <https://github.com/operator-framework/operator-lifecycle-manager/issues/1685>
