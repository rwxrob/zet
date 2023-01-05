# Complexity Contained, Isolation Brings Simplicity

The entire cloud-native thing has added several layers of complexity to
just about everything, but one area that has been simplified is dealing
with *only* the stuff running in a container. 

For example, today I've been working with JupyterHub (creating a portal
that is aware of NAS user space) and while debugging the
*VirtualService* I started a web server with `python3 -m http.server`
(since Python is already here) and was able to immediately identify the
one of --- wait for it --- *four* total processes running on the
machine. That's fucking insanely simple to diagnose and work with. You
should see how simple `/proc` is.

This simplification is well appreciated by a guy like me who has had to
sift through upwards of hundreds of applications running on the same
system in different capacities. This makes application debugging ---
even while running in production --- an absolute dream compared to
before. It is this isolation that brings simplicity with it. It might be
as confusing and complex as hell to deploy and get to, but once you are
working with a contained application inside a cluster it is *way*
simpler. Hell, you can even fuck up the thing while messing with it in
production and just kill it so that it gets immediately replaced with a
new one. *That's* the beauty and value of Kubernetes orchestration.
