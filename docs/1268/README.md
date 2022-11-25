# Install Elasticsearch (ECK) Colearning

📺 <https://youtu.be/WXP7Jhhomj8>

1. Create a 4-node Minikube cluster (for simulated HA)
1. List labels for a specific node
1. Attempt to trick ES by adding topology zone labels to nodes 
1. Pain points when using Helm include agreement on identifier
1. Attempt to install with Helm 
    1. Add the Elasticsearch Helm repo
    1. Evaluate the Helm template 
1. Discussed limitations of Helm
1. Discussed strategies for working around Helm constraints
1. Beginner look at StatefulSets

Related:

* Well-Known Labels, Annotations and Taints \| Kubernetes  
  <https://kubernetes.io/docs/reference/labels-annotations-taints/#topologykubernetesiozone>
* <https://icepanel.io/>
