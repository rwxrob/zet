# Local (On-Prem) Kubernetes Requires DNS Server

At least one critical application that I need to test locally in my own
on-prem k8s cluster will need an internal DNS server. Making changes to
`/etc/hosts` files will not cover this. Specifically, Harbor with
Ingress requires DNS to resolve properly. This is one reason I have been
saying to anyone interested in getting into this "infrastructure
engineering" stuff if that you can't just learn Docker and Kubernetes,
there is a *ton* more that you need before you can even venture into it.
This is why *true* Infrastructure Engineers make so much fucking money.
They have to be uber-admins before they can even get into and fully
understand a full on-prem Kubernetes deployment. I've been a good admin,
but this stuff makes me feel like a junior all over again. I haven't
setup and maintained my own internal lab networking services since the
90s. Looks like I'm gonna be doing all of that and more.

I feel an architecture diagram coming on, specifically, to clearly
delineate the components that are within the Kubernetes cloud and those
that any Kubernetes on-prem architecture critically requires, such as
the following:

* DMZ Network
* Netboot Server
* NAS Server
* DNS Server (upstream to whatever, 8.8.8.8 perhaps)
* LoadBalancer (just round-robin DNS)

Then there is the question of whether to setup HA on these critical
services or not. At a minimum, I should have two DNS servers configured
and synced. Then we have to setup all the security monitoring in
addition to this. I'm thinking a couple (maybe three) Raspberry Pis will
be absolutely fine for DNS and TFTP for Netboot.

Related:

* Build a Kubernetes cluster with the Raspberry Pi \| Opensource.com  
  <https://opensource.com/article/20/6/kubernetes-raspberry-pi>
* The state of netbooting Raspberry Pis  
  <https://blog.alexellis.io/the-state-of-netbooting-raspberry-pi/>
* The 10 Best Free and Open-Source Identity Management Tools  
  <https://solutionsreview.com/identity-management/the-10-best-free-and-open-source-identity-management-tools/>

Tags:

    #k8s #dns #prereqs #onprem
