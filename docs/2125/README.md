# Podman Desktop chooses kind for Kubernetes

Noticed this week that Podman Desktop now asks to install the `kind` binary for Kubernetes support. I think this further solidifies `kind` as a required-learning tool over `microk8s` or `minikube` even though the others will be on most certification exams. Having looked at the internal code in all of them I can say that the coding quality of `kind` is far better than the others. (It was in the `kind` code base that I learned about grouping extraneous YAML settings into a single catch-all so that the rendered YAML file would not truncate them.)
