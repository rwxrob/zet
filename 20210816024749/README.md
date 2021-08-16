# Kubernetes `kill -9` Pods Stuck in 'Terminating'

The more I get familiar with Kubernetes the more commonality I see to
stuff for dealing with plain 'ol processes. I realize a "Pod" is not
a process but you can really kind of think of them as such when wrapping
your head around the many different management tasks involved.

For example, I recently blew an hour trying to get a GPU feature
discovery DaemonSet to terminate all its pods so I could test my new
filter configurations with `whiteListLabels` in
`node-feature-discovery`, but pod stuck in 'Terminating' state just
would not die. It immediately reminded me of a process that won't die
politely, or worse, a TCP/IP connection hanging on FINWAIT (you what I'm
talkin' 'bout \*wink\*).

I did all sorts of PD, even went on the system and saw all the problems
that underlying node OS is having, and reported them. I even found
a server configuration in the `/etc/ssh/ssh_config` client configuration
that blocked all `ssh` from working (which made me chuckle, at someone,
while I commented it out) but no joy with my hung pod (which reminds me
of a well-endowed, body-snatcher for some reason).

I thought of rebooting the node, but that seemed like overkill. Safely
rebooting is not just a matter of `shutdown -r now` because you need to
at least try and "drain" the node first to make sure everything gets
resheduled safely.

Then I found this:

    k delete pod NAME --grace-period=0 --force -n NAMESPACE 

Yep. It's the `kill -9` I was looking for. It came right down.

Obviously, since this command tells the K8S stuff in the control plane
to just "forget about it" this isn't something to be done lightly, but
neither is `kill -9` when a simple and polite `kill` will due just fine
(in most cases).
