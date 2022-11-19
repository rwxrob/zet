# Use Curl with UNIX Socket

The amazing `curl` strikes again. Using the following allows the
querying of a UNIX socket as if it were a web site with a REST API. This
is how Docker does everything from `/var/run/docker.sock` (which is just
so fucking brilliant on the part of the Docker team).

```
curl --unix-socket /var/run/docker.sock http://localhost/version
```

This returns a bunch of JSON that can easily be parsed with `jq`.

Obviously, this means all you have to do is bind-mount that file (from
WSL2 in Windows) in order to use the same Docker within your container
as the host system. You could even set up a Docker-ception if you
wanted.

This has massive implications for those wanting to use containers as
snap-able images of their working environment, much like people have
used VMs in the past.
