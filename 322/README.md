# Install Elasticsearch (ECK) Colearning

📺 <https://youtu.be/uCyM5zwa9Ss>

1. What is Elasticsearch and ECK? (Elasticsearch Cloud on Kubernetes)
1. Consider installation methods:
    1. `kubectl apply -f ...`
    1. Helm Chart
1. Which Kubernetes cluster should we use?
     * Rumor has it Minikube doesn't work (but we'll test)
     * Let's go with Kind
1. Create a lab repo for GitHub
1. Research on number of Nodes needed
1. Discovered `topology` label for zone affinity and distribution
1. Ranting: DevOps isn't enough (cross-over knowledge needed by both)

Related:

* Quickstart \| Elastic Cloud on Kubernetes \[1.8\] \| Elastic  
  <https://www.elastic.co/guide/en/cloud-on-k8s/current/k8s-quickstart.html>
* Install ECK using the Helm chart   
  <https://www.elastic.co/guide/en/cloud-on-k8s/master/k8s-install-helm.html>
* Install Elasticsearch on Kubernetes Using Helm Chart  
  <https://phoenixnap.com/kb/elasticsearch-helm-chart>
* High availability Elasticsearch on Kubernetes with ECK and GKE \| Elastic Blog  
  <https://www.elastic.co/blog/high-availability-elasticsearch-on-kubernetes-with-eck-and-gke>
* How To Deploy the Elastic Stack in Kubernetes With ECK   
  <https://raphaeldelio.medium.com/deploy-the-elastic-stack-in-kubernetes-with-the-elastic-cloud-on-kubernetes-eck-b51f667828f9>
* Well-Known Labels, Annotations and Taints \| Kubernetes  
  <https://kubernetes.io/docs/reference/labels-annotations-taints/#topologykubernetesiozone>
