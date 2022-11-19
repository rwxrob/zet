# Add Namespace Exception to Gateway for NFD

Adding Node Feature Discovery (and Nvidia's extension, GPU Feature
Discovery) requires adding an exception to the Gateway `config`
resource. Without it only the master will appear, not the worker nodes.

```
k -n gateway-system edit config
```

Then, assuming your namespace is `node-feature-discovery`:

```yaml
apiVersion: v1
items:
- apiVersion: config.gatekeeper.sh/v1alpha1
  kind: Config
  spec:
    match:
    - excludedNamespaces:
      - node-feature-discovery
```

Without this it just doesn't work. By the way, if you didn't have this
before you just have to add it without doing any `helm` commands at all,
it will detect the change and bring the worker nodes online.

If you are still having trouble, do `k get daemonset` to see the errors.

    #k8s #gateway #nfd #pd #helm
