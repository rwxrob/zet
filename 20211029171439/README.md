# Kubernetes Applications Development (CKAD) Colearning (rwxrob.tv)

1. Seems like there are two approaches to CKAD
    1. Understand concepts and patterns for applications development
    1. Install and configure existing application
    1. Create and deploy new applications
       * "init, sidecar, app, load-balancing, database + pv"
1. Pick a project for each
    * Deploy ElasticSearch (ECK stack)
    * Deploy Istio
    * Build an online / live community (not as related)
    * (Note that rwxrob.tv schedule will have specifics)
1. What Kubernetes platform on which to build?
    * Prioritizing an authentic experience for *true* learning
    * Minikube
      * "Doesn't have good PV emulation or support" (black_mou5e)
    * Kind
      * The darling of the Cluster API world
      * Built specifically to do Kubernetes development and testing
    * Cloud
      * Expensive to get all the nodes to model complex deployment
    * k3s / microk8s
      * Not a full Kubernetes implementation
      * Specifically designed for small-scale IoT/Edge implementations
    * Hardware
      * Obviously the best, just takes a lot of infra work to setup
      * No yet ready
      * Building out IRL on stream starting next week

Related:

* Open Source Curriculum for CNCF Certification Courses  
  <https://github.com/cncf/curriculum>
* 20210727192135 Kubernetes Node Feature Discovery
* 20210809204022 Filter Unwanted Labels in Node Feature Discovery
* 20210816052811 Node and GPU Feature Discovery Namespaces Combined
* 20210601174906 Istio Sidecar Injected Into Kubernetes Pods
* 20210611135245 Istio *Gateway* and *VirtualService*, Not *Ingress*
* 20210614141110 Istio VirtualService `host` Actually Means Service
* 20210819185315 Istio Fucks Up `kubectl run`, Forever
* 20211029175451 🖼️  Istio Architecture
* 20211029180346 🖼️  Istio Architecture
* 20211029182124 🖼️  Istio Covers What Kubernetes Does Not
* Why Kubernetes is The New Application Server \| Red Hat Developer  
  <https://developers.redhat.com/blog/2018/06/28/why-kubernetes-is-the-new-application-server#empowering_your_application>
