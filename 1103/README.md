# Don't Forget to `apt-get upgrade` in Dockerfiles

Usually `FROM ubuntu` and the like are not enough. You still have to
make sure you have the latest version of the operating system and its
security patches --- especially if you are considering a workspace
container.
