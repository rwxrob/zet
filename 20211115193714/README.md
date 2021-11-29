# Operator Lifecycle Manager (OLM) is Dangerous

The Operator Framework is a disastrous, irreparable failure. OLM with
full cluster-admin privileges is just Helm 2 Tiller all over again, but
worse. Not only does OLM require enterprise root (my term for
cluster-admin to your entire cluster) but it also *requires* access to
the Internet to pull operators from their hub to then be run as root.
You can forget about being "air gapped" at all. You would think all the
stuff RedHat spews about Docker and running as root that someone would
have said something before this monstrosity was ever released. No one
should *ever* consider using the Operator Framework, period. In fact, my
confidence in RedHat in the cloud-native space is now at an all-time low
after discovering this. This is just idiotic architecture. They've had a
ticket open for more than a year pointing out this massive security risk
and the responses are downright juvenile:

> ⚠️
> The OLM approach to K8S software installation and management does not
> provide for organizations with "air gapped" policies and architecture.
> It simply does not work without Internet access to `operatorhub.io`.

> ⚠️
> Operator Lifecycle Manager (OLM) runs with cluster-admin privileges.
> ...
> Cluster administrators should take measures to ensure that an Operator
> cannot achieve cluster-scoped privileges.

Here is the ClusterRole requires by OLM:

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
