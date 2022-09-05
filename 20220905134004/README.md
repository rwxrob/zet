# Distributed Bonzai Monolith (z) Network

Recently I realized that the concept of a Bonzai monolith (mine is
called `z`) could be expanded into a distributed network of identical
endpoint agents where any single endpoint can be graduated to a main
controller simply by being given the knowledge of the others and the
private key matching the distributed public keys of all the others.

Because it is a core concept of Bonzai monoliths that they change
frequently with updates and new functionality, these keys can be
embedded in an embed.FS within the binary itself. In fact, the private
key can be safely embedded so long as it is asymmetrically encrypted
with a very substantial passphrase.

The more difficult task would be discovery, even over a local subnet.
Broadcasting packets make the most sense, but are not always reliable.
A controller could broadcast to everything on the subnet that there is
something to do, and any client that hears it could then contact the
controller directly to get the details of the work to be done. The
broadcast method does not require than any controller even know about
other endpoints on the subnet, but could easily cache them for the next
time. Additionally, when a new endpoint is added, it could be told the
IP of its current controller and check in with it to register itself in
the list of endpoints, which could be maintained only in RAM, or to an
encrypted temporary file.

Later, the need to propagate work to other subnets would also be needed.
Each endpoint could be setup to echo the broadcast to all currently
available subnets on that specific endpoint as well. There might be some
danger of looping through different interconnected networks, but this
could be avoided by limiting the depth.

In situations where broadcasting to subnet isn't desirable an optional
list of IPs could be provided in a file, or a "stealth" mode enabled
that quietly scans the subnet for any hosts listening on the specified
port. When any new endpoint is started up, it would still register with a
specified controller. For further stealth, endpoints could register with
completely different port numbers, even rotating port numbers on given
intervals and updating the controller of the new port.

All of this could itself be implemented as a Bonzai branch that anyone
could easily add to their own tree monoliths. I'm thinking `agent` would
be the name. The `agent` branch would both manage the distributed
network, and broker calls to other available Bonzai commands simply by
calling itself internally, which has the added benefit of keeping the
passed command line arguments from being visible in `/proc` and
elsewhere. Someone would have to be doing a live `strace` to see
anything the process is doing. The protocol for agents to communicate
with one another could be `mTLS + gRPC`.
