# Update annotation to trigger rolling restart synced to configmap

```yaml
spec:
  template:
    metadata:
      annotations:
        configmap-version: v1
```

By just updating that one annotation you save the hassle of firing off a rolling restart when a change is made to the associated `ConfigMap`. This plays nicer with scripting as well.
