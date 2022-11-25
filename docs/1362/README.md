# ElasticSearch Log Volume Capacity is Crazy

I cannot give away too many details since this is a work thing, but I'm
absolutely blown away by the volume of incoming log data that
ElasticSearch is able to handle. We have a significant number of nodes
sending 2-3 messages a *second* and hundreds of thousands of nodes. Want
to "grep" all the logs? Write an ES query (which I'm about to do now).
You can even setup deployments within the Kubernetes cluster to respond
in any number of ways to stuff detected in the log queries and take
proactive action to remediate. This is where stuff like Kubernetes
starts to make sense. This type of thing would be a totally different
beast in a VM only architecture.
