# Filter Unwanted Labels in Node Feature Discovery

📺 <https://youtu.be/Plo9nuZFAfU>

Kubernetes *Node Feature Discovery* gives you insight into what is on a
given node so that you can more accurately map deployments to nodes that
match what you need. This is particularly important when working with
heterogeneous architectures and some that may or may not need graphics
cards. However, the default for NFD produces far more labels than you
probably need.

The (undocumented) solution is to set the
`worker.config.core.labelWhiteList` to a regular expression matching
only those you wish to see.

```
worker:
  config:
    core:
      labelWhiteList: '^(custom|system|pci\-03)'
```

