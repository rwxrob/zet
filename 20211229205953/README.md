# Home Kubernetes Infrastructure Lab

Considerations:

* Want a phased approach that can be easily taught with quick results
* First phase should be slightly harder than setting up Kind multi-node
  cluster on a single machine

Questions:

* Which system should receive externally forwarded SSH main traffic?
* Should I start with Netboot setup? Or just plain systems at first?

Phases:

|:-:|-|
| zero  | multi-node Kind (Docker) cluster |
| one   | multi-node physical cluster |
| two   | + high availability zones |
| three | + netbooting nodes |
| four  | multiple multi-node physical clusters |

Clusters:

I am keeping the hardware in each cluster as homogeneous as possible
just to keep the infrastructure management simpler. I realize this will
give me less opportunity to "train" on heterogeneous deployments (like
at my present employer) but it is always best when you have the option.
In fact, I want to train myself in working with the *best* solutions at
home, not reproducing the cluster-fucks at different places of
employment.

* Mac Minis
* MSI Tridents
* Raspberry Pis 
