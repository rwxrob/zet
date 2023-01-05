# Use `items:` for Multiple Resources in Single Manifest

Today I learned after running the `kompose` tool against a rather
complicated application (Icinga) that the fastest possible way to create
a lot of new Kubernetes resource items is not by separating them with
`---` as separate manifest files, but using the `items` keywords and
putting them all effectively in the same resource file, which appears to
create only a single API call.

This method has its drawbacks though since it forces a level of
indentation that is pretty ugly.

```yaml
apiVersion: v1
items:
  - apiVersion: v1
    kind: Service
    metadata:
      annotations:
        kompose.cmd: kompose convert -o komposed
        kompose.version: 1.26.1 (a9d05d509)
      creationTimestamp: null
      labels:
        io.kompose.service: icinga2
      name: icinga2
    spec:
      ports:
        - name: "5665"
          port: 5665
          targetPort: 5665
      selector:
        io.kompose.service: icinga2
    status:
    ...
```

Tags:

    #k8s #yaml #tips
