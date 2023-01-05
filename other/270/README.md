# Use `k config view --minify` to Get Current Namespace

It's not particularly intuitive, but to lookup the current active
namespace, something that changes frequently when working on debugging
a Kubernetes running application, requires `k config view --minify`,
which removes anything but the current active context.

```bash
k config view --minify -o jsonpath={.contexts[0].context.namespace}
```

I have this in a script by itself, but add it to others as well.

Whenever possible I've found it far more helpful to change the entire
context and take the time to setup contexts properly so that I can just
switch between them and save a bunch of `--namespace` options when
necessary.

    #k8s #tips #scripts #contexts #namespaces
