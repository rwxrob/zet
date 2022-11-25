# Just `ssh` to Control-Plane Node, Then to Any Node

Wasn't able to get any answers from the Internet about how to get onto a
Kubernetes node to see its `/var/log/messages` file (which you cannot
get to without being on the node itself). But I figured it out by just
`ssh` connecting to one of the control plane nodes (as identified by
`kubectl get nodes`) and then `ssh`ing directly into the node by host
name. I didn't even need to provide any credentials. Apparently, logging
into all the Kubernetes cluster took care of all of that. I assume that
is what is up with the credentials stored in `~/.kube` but I don't know.
Back to work. Next task, scripting something quickly that looks in all
the node `messages` logs for the same problem. I would think these were
captured by something in Kubernetes or ElasticSearch but doesn't look
like it. Maybe we have a Splunk or something around I'm not aware of
yet.
