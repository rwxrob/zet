# Use `k rollout status deploy ...` to Wait in Scripts

Despite the existance of `kubectl wait` it looks like `kubectl rollout
status deploy <deployment>` is more reliable. Adding it to a script
causes it to block until the deployment is ready ("rolled out").

    #k8s #scripts #tips
