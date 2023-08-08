# Configuring and debugging Calico BGP in Kubernetes

BGP came out in something like 2007 and I *really* need to deep dive into learning everything about it. It is at the core of all network operations within Kubernetes using the most important CNI implementation, Calico. When peers cannot get their information and they timeout forcing network CNI reboots randomly that kill any applications that to their own liveness probes.

* Configure BGP peering \| Calico Documentation  
  <https://docs.tigera.io/calico/latest/networking/configuring/bgp>
