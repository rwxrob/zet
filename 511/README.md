# See All Pods on a Given Node

Unfortunately, there is not a short version of `--field-selector`.

```
k get pods --field-selector spec.nodeName=NAME -A
```

