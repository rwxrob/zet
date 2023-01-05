# Start Thinking Multi-Cluster from the Outset

I'm still a noob with Kubernetes architecture, but I'm beginning to have
a strong opinion that it is better to think early about what the
clusters (plural) will eventually be in your environment and not the
cluster (singular). The place I work now has really worked themselves
into a corner by not anticipating the need for multiple clusters later.
Small decisions, like maintaining an external etcd, are now impacting
the ease with which we deploy additional clusters for other reasons.

Even though Kubernetes takes care of Node affinity and has taints and
tolerations to help isolate Nodes during selection, the unnecessary
complication of this when deploying to Nodes on a vastly heterogeneous
hardware collection adds unnecessary overhead and risk. It seems better
to think of the clusters in terms of hardware similarities and to build
them that way from the very beginning.

I'm still unsure because the work of setting up and maintaining an HA
control plane isn't trivial and burns several machines in the process
(which is a factor at home when I don't have that many to begin with)
but I'm still going to think about multi-cluster from the beginning
more.
