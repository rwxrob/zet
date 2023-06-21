# Error when minikube doesn't have CA matching OIDC provider

When attempting to do any command with `kubectl` against a minikube cluster that has not had the root CA added to `.minikube/certs` before creation the following misleading errors occur:

```
E0619 13:39:00.701338    5658 memcache.go:265] couldn't get current server API group list: the server has asked for the client to provide credentials
error: You must be logged in to the server (the server has asked for the client to provide credentials)
```

This is really the K8S API server complaining that it cannot authenticate the OIDC token passed by `kubectl`.
