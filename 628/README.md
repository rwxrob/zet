# Host containers

It's hard to identify a computer these days. So many different things can run an operating system while appearing to be completely different distributions of that OS. We have virtual machines, containers, hypervisors, and more. So knowing what to call something is really hard. I've heard all of the following terms used for the same thing:

* host
* machine
* node (network)
* node (Kubernetes)
* compute instance (Google)
* workspace
* desktop
* server
* system

Some of these are qualifications on how that thing is used.

I feel like *host* is the best term of all, after all, every computer on the network has to have a `hostname`, so they are definitely hosts, but are they?

Just because it has a different MAC address doesn't mean it is a machine. Containers have really blurred those lines. So when using a container as a logical host I feel like calling it such is enough distinction. So host containers it is.

This compliments the term I use for a container running everything I need from the terminal to get work done, which I call a **workspace container** and use every day from Docker Desktop on Windows (that I'm forced to use by my employer).
