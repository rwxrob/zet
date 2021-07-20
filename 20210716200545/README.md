# Which Single-Node Cluster to Learn On?

* `minikube`
  * Virtual machine with Kubernetes inside
  * Harder to get access to anything
* `kind`
  * Invented to test Kubernetes itself
  * Uses docker for private registry
  * Seamless cluster creation and tear down
  * Now being used in CI/CD related to Kubernetes
  * Easy to access from local system
  * Not restricted to just a single node
  * Easy to create and tear down a cluster
* `microk8s`
  * It *is* Kubernetes in every way
  * Tougher to tear down and create 
  * Maybe preferred for a *real* local lab

