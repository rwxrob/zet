# Use `netshoot` to Peek Inside Your K8S App

TIL there's a thing called `netshoot`. It is an ultra-lightweight
workspace container with all the network essential tools in it. This is
the perfect thing when trying to make sense of domain name resolution
and networking, which can get really hairy really fast in Kubernetes.
Here's how to just run one pod and have it delete ("Terminate") after
you exit:

```bash
#!/bin/bash

exec kubectl run netshoot --rm -it \
  --image nicolaka/netshoot \
  --namespace "${1:-$(ns)}" \
  -- /bin/bash
```

This accepts a single argument for the namespace since that is often the
thing that changes and isolates the scope of a cloud-native application.
(You would have to have the `ns` shortcut command for this to work.)

Also see:

* [20210818180340](/20210818180340/) Use k config view --minify to Get Current Namespace

    #k8s #tips #netshoot #networking #cloud

