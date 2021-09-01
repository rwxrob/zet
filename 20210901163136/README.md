# Containerized (Kubernetes) Achievement Server (skilstak.sh)

I still have `skilstak.sh` and there's nothing really going on now that
I don't do private mentoring any more. That used to be the place to
login and get stuff done while learning. Now I'm thinking with the
`skilstak.io` eventual rebranding as an educational achievement platform
that `skilstak.sh` could spin up a container with mounted PVC upon
connection from `ssh`. I could use all the architecture I'm learning
about for the JupyterHub Kubernetes install to drive the same thing. The
result will end up looking similar to other web-based terminals but
without the overhead and would allow (and encourage) direct `ssh` access
to it via public key. The keys could be mapped to Secrets that are also
mapped to Namespaces for each user in order to keep track of them and
make them expire over time.

The cost to do something like this in the cloud would be far too
prohibitive, but using my own personal Kubernetes cluster at home would
work. It's basically the same `skilstak.sh` I had before, but without
the multitenancy concerns. Everyone would have their own account. And
God knows I would catch anyone attempting to use their container/server
for nefarious purposes. There would be no need to reveal any private
information about oneself and before encouraging the usage of it I would
give everyone a crash course in using a VPN if that is their concern
(even though a doxed IP is really nothing to be concerned with these
days). People would have to just do things that they would not mind me
snooping and watching. I probably wouldn't, just because I don't have
time, but I would make that part of the terms to keep things above
board.

Another possibility would be to wipe each container after every
disconnect, which is ridiculously simple with Kubernetes.

Hell, the educational application of this is just mind-boggling. I
finally know what I *really* want to do with my personal Kubernetes
cluster once I have it built.

    #skilstak #education #achievements #coding #beginners
