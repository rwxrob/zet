# Istio Sidecar Injected Into Kubernetes Pods

Today I learned (just from running into it) that Istio, if installed
into your Kubernetes cluster, will inject what it calls a "side-car"
into *all* pods deployed into that namespace for which Istio has been
configured. The most noticeable immediate side effect of that is that
you now have to pass `-c <container>` to your `kubectl exec` calls
when connecting directly to a running node. You'll see a prompt that
looks something like this when you connect:

```
istio-proxy@jhub-rwxrob-67cf4fcf8c-rlqbh:/$ 
```

