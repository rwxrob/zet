# CN Admin Requires CN App Development

The more I work on this rather large Kubernetes cluster the more I
realize that the equivalent of writing a quick Python Fabric script
(remember fabfiles?) to detect and remediate an issue is a much bigger
deal in an enterprise cloud-native environment. The multiple levels of
complexity make easy scripting like that virtually impossible, but not
out of reach. 

The task we are facing at work is to remediate something that we see a
lot in `/var/log/messages` (by way of ElasticSearch) and then trigger a
remediation by way of a dynamically created Kubernetes Job or passed
along to a remediation bot (Deployment) listening for things to fix.

So, it would seem that anyone who calls themselves a "Cloud-Native
Administrator" should really be able to quickly create a k8s Job or
Deployment (bot) to do the administrative tasks required on the cluster
and even its Nodes.

Why does anyone care about this conclusion? 

Because it means that getting the equivalent knowledge of a CKAD is
critical to *all* roles in cloud-native operational support. In other
words, learning to create k8s applications (deployments and jobs), is
the same as learning to code if you are an "SRE" (an admin who codes).
In fact, if an SRE is "an admin who codes" then a Cloud-Native Engineer
is "a cloud-native admin who codes cloud-native apps." And let's face
it, you can't even begin to create cloud-native apps until you can code
in POSIX shell, Bash, Python, and Go (at least the kind of apps needed
for this work).
