# Use `watch k get po` to Watch New Deployments

One of the key commands I find myself doing all the time is `watch k get
po` (`kubectl`) to see the transitions of the state of my new deployment
being terminated and started up. As a beginner I cannot overstate how
much this helped me actually visualize what is actually going on. The
whole Kubernetes thing sometimes feels like you are throwing things into
the ether and hoping it just works. This little command is like the
equivalent or run or compile or build during other phases, except it
almost always is directly related to getting the fields of your YAML
correctly. If Kubernetes and cloud-native people are just "YAML
programmers" then this is how you "run" your YAML and see the output.
