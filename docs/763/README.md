# Kubernetes: "No Root for You"

While Docker has gotten a proverbial black eye over running with root
privileges, people coming to Kubernetes from Docker are like, "WTF!
Where's my root access?" This is because unless you explicitly set the
`securityContext` you don't get root access. This can be annoying during
development and debugging because you cannot change anything on the
container that matters. You don't have `sudo` (unless you added to the
image, which is a bad idea even during development). Hell, you don't
even have `vi` (which is why you went to the trouble to mount something,
mostly like NAS so you could even get files onto it live). In fact, the
only way to get onto the system is with Docker. You really should not do
this, but you *could* get to the Node directly (with `ssh`, etc.) and
run `sudo docker exec -it -u root <id> bash` (or whatever). Ironically,
it takes a "local" docker running on the node/machine to get root unless
you provide it some way explicitly through the Deployment itself.
