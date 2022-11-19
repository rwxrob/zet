# Show Everything with `helm get manifest`

📺 <https://youtu.be/GNAtVEY9tUU>

Ever want to see *exactly* what applying a Helm chart has done do your
cluster? Use `helm get manifest` to see all the YAML as if it had been
passed to `kubectl apply -f FILE` where the file is a huge YAML file
with all the Kubernetes resource definitions combined.

You can even pipe to `kubectl get -f -` to see what you would see for
each resource with `kubectl get`.

I really love this because it provides a way to see what changed by
storing the output over time as you make changes to the Helm chart or
need to distinguish what was changed by the Helm chart from other stuff
you have changed to get the Helm chart to install in the first place
(RBAC, etc.).

    #k8s #helm #tasks
