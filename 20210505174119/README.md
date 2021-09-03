# Install WSL2 for Docker Desktop on Windows

As much as I have complained about WSL2 bork file system mounting and
all the bugs with handling OpenConnect VPN (the firewall blocks without
adding complicated PowerShell scripts that run on every connect) it
still makes sense to install WSL2 first because (I just learned) it
makes Docker run *a lot* faster. It has something to do with Docker
leveraging the kernel used by WSL2 instead of something else. I hate
that this level of complication is required to get containers on
Windows, but once Docker Desktop is installed things are fine.

Another reason to do this is to make it easier to run `docker` inside of
any other Linux container by bind-mounting `/var/run/docker.sock` (or
whatever). You can do that without WSL2, but it is just easier if you
have it. (The paths are easier, for one.)

Most people will never need more than WSL2 in the first place despite
the annoyances I have described. In fact, I'm a little annoyed that
people have to install WSL2 just to get Docker on their in any
reasonable fashion. I honestly wonder if it easier to just install Linux
on the hardware and be done with it. But containers are still the basis
of all the experimentation and learning from Boost (and just in general)
so starting with Docker is always the right path.
