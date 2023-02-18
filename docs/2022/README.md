# Hashicorp go-plugin has one show-stopping flaw

The otherwise amazing go-plugin module simply cannot be depended on when putting plugins into their own containers. The entire thing has been designed to run on the same machine. In fact, there is a big warning about "running over the network." This is rather ironically *not* how cloud native development works these days.

I've discovered that when reaching for a "plugin" what I really want is a "service", you know, as in Kubernetes Service. By making it a service, instead of a localized plugin, I get the option of running it in a container, as a daemon on the same machine, or as one of many Pods in a Deployment that are synchronized and auto-heal when then go wrong.

This flaw kills go-plugin for pretty much anything I would ever want to make.
