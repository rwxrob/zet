# Node and GPU Feature Discovery Namespaces Combined

It's far to unclear from the documentation, first, how to limit labels
you want to appear, but also, that when adding other Node Feature
Discovery stuff (such as NVIDIA's GPU feature discovery) that the
namespaces are actually combined.

First make sure you have your `.master.extraLabelNs` set to `-
nvidia.com`. This effectively causes `feature.node.kubernetes.io` to be
fused (and ignored) with `nvidia.com` so that the
`worker.config.core.labelWhiteList` regular expression starts after the
`/` in *either* of them.

You might struggle initially with what the regular expression actually
is. To me intuitively I thought `nvidia.com` needed to be included, but
as I just explained, that's wrong. Instead, you just add the prefixes
from the `nvidia.com` namespace is if they were all combined with
everything from `feature.node.kubernetes.io`. Adding `cuda|gpu|gfd`
currently grabs all the stuff in `nvidia.com`.

```yaml
worker:
  config: |
    core:
      labelWhiteList: '^(custom|system|pci|cuda|gpu|gfd)'
```

Also do not forget to set your `nodeSelector` in the GPU helm chart
(DaemonSet) and that you include that label to link to in your white
list (ours is `pci-0` something).

    #k8s #nfd #gfd #gpu #featurediscovery #kubernetes #tips
