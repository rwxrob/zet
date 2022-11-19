# Containers Leave No Trace

One of the least appreciated things about containers to beginners is
that they leave absolutely no trace that they were ever run on the
system once removed. This also means that anything auditing the host
system won't be able to see into them as well.

Want to use Linux but putting Linux on your host operating system is
banned by your fucking idiotic IT department? If they allow Docker to be
installed --- and you have admin rights --- you can use a container to
run any Linux you want, yes, even Arch. Arch in the enterprise. Who'd of
thought?

There are so many other reasons this is nice including working on a
laptop or computer you don't particularly trust. Other than a key-logger
it is very unlikely that the host can know what you are doing in your
container.

Technically, a host could run some crazy software that detects docker
and audits the running containers and checks their type and logs into
them. But this stuff is non-existent right now. If you run a container
within a container this is virtually undetectable.

This has huge implications for IT professionals in general, but is
particularly valuable to security professionals from any industry.
