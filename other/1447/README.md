# Kubernetes Endpoint Object Like Round-Robin?

I know it is unrelated, but the first thing that came to mind reading
about the *Endpoint* Kubernetes object (as described in the
*Services*) is that it is like assigning multiple IP addresses to an
old-school DNS name which results in the DNS servers rotating around
through them in "round robin" fashion (if they even still do that, it
was like two decades ago that I worked with DNS like that). Here's the
excerpt that triggered that thought:

> An Endpoint is an object that gets IP addresses of individual Pods
> assigned to it. The Endpoint object is then in turn referenced by a
> kubernetes Service, so that the Service has a record of the internal
> IPs of Pods in order to be able to communicate with them.

I haven't figured out if the way connections get distributed is a matter
of Service policy or not. I imagine it is.
