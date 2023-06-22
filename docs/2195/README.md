# How to get current k8s context using client-go

Here is the official way, but it comes with danger since it doesn't work consistently across versions client-go (which is why k8s source locks down the version of a third-party dependency). It also brings in about 30 dependencies into any project that uses client-go.

```go
    config, err = clientcmd.NewNonInteractiveDeferredLoadingClientConfig(
        &clientcmd.ClientConfigLoadingRules{ExplicitPath: pathToKubeConfig},
        &clientcmd.ConfigOverrides{
            CurrentContext: "",
        }).ClientConfig()
```

It is actually simpler and safer to just marshal the JSON from `kubectl config view -o json` instead.

* kubernetes - How to get current k8s context name using client-go - Stack Overflow  
  <https://stackoverflow.com/questions/70885022/how-to-get-current-k8s-context-name-using-client-go>
