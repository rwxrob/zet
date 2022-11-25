# What if Kubernetes on metal reduces power needs?

Miluba made a comment in YouTube about Kubernetes on metal with net boot
possibly reducing power bills. I hadn't really thought of it, but this
could significantly reduce costs for the enterprise by allowing certain
nodes to "sleep" (we'll say) when not in use. Kubernetes could maintain
a buffer of active systems so that there would never be any lag, but
imagine the cost savings to allow all of that hardware to be managed and
scaled as if it were pods.

There's a good chance this won't come from the cloud providers because
they love all the idle nodes running and burning up billable CPU. But
Amazon, at least, championed elastic infrastructure as a marketing
method and maybe would see the value of K8S-on-Metal to allow for this,
but since everything on Amazon is already virtual maybe not. It is going
to take more enterprises to realize that running K8S on virtual servers
is 30% less efficient to create the market pressure to provide a bare,
on-metal solution.

This is all very intriguing and tends to make me believe more strongly
that K8S-on-metal is the future (at least from where I'm sitting).

Tags:

    #k8s #cloud #talos #sidero #metal #devops #infrastructure
