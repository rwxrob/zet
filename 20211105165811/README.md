# Kubernetes Colearning, Nov 5, 2021

📺 <https://youtu.be/f3tGXM6EsZk>

* Docker Desktop enterprise remediation
  * Not* FOSS
  * Now charging for it 
  * This is the reason FOSS people *hate* Docker
  * Kubernetes people really don't like Docker
  * Minikube doesn't work because require either Docker or VM software
  * Let your users/developers/engineers use Linux workstations
  * People who use/know Docker Desktop already know Linux
* Check a Helm deployment against OPA Gatekeeper policy *before* install
  1. (None of this requires a Kubernetes cluster)
  1. Install Helm chart
  1. Output the Helm chart resource YAML
  1. Apply Gatekeeper policy checks
* What the hell is OLM and <https://operatorhub.io>?
* Following NFD project says a lot about preferred install methods
  * Looks like Operator Framework is overtaking Helm in popularity
  * Also Kustomize is holding on as well for smaller deployments
* Does my enterprise require "air gap" separation from "package"
  providers?
* Good practice to interrogate and scan any images added
* Bad Helm charts inevitably do not allow changes to image source
* New appreciation for Helm's concerns for "air-gapped" requirements

Related:

* <https://kubernetes-sigs.github.io/node-feature-discovery/v0.9/get-started/deployment-and-usage.html>
