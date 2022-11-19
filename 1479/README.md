# Just Use Docker Desktop

I realize this is the polar opposite of my complaining about using
Docker Desktop (which has .Net dependencies that were killing things),
but after struggling with other problems running `dockerd` from within
WSL2 I now know (probably) why that is recommended *against* by the
Docker company and team. I just doesn't fucking work reliably. The
levels of network tunneling involved when doing that really mess
anything you would do with the `docker` command up. Also, you have to
manage all your own network setup because you don't have Docker Desktop
confidently taking care of everything using the higher network in which
it runs, which includes recognizing the tunnels created with AnyConnect.

In short, running a workspace container within Docker Desktop with WSL2
is the single most reliable way to get work done consistently. Just
don't forget to `chown <you> /var/run/docker.sock` and mount it so that
you can use `docker` from within the container running inside of WSL2.

By the way, this also works for using my workspace container in *any*
Kubernetes cluster so that I have my own, sort-of personal "server" in
any application namespace where I need to have visibility into the rest
of the stuff running within the cluster.
