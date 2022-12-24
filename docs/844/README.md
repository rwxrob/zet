# Learn Golang for Cloud Native / Kubernetes

Even if you never plan on becoming an applications developer, learning at least a minimal amount of Go programming --- specifically Go template language --- is an absolute must. Here's a sample from a standard documentation page:

```sh
kubectl get pod termination-demo -o go-template="{{range .status.containerStatuses}}{{.lastState.terminated.message}}{{end}}"
```

One of the most important output formats is `go-template`. All of this could easily be done with `jq` as well (in fact, learning `jq` is far more important that learning Go template language), but still, Go is what all of this is written in to begin with. You can open up the source directly and get your answers when nothing else is available as a last resort.
