# Default `docker.io` Registry Domain for Images

I had some question about whether the default domain in the image path
might be `hub.docker.io` and it is `docker.io`. It is implied whenever
using `docker` but sometimes putting it explicitly makes a lot of sense,
especially since `podman` is a thing (that I don't like, but whatever)
and it will likely not default (or perhaps other tools might not).
