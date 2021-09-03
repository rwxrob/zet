# Add Docker Volume Mount After Running It

It's not particularly obvious to beginners (like me) that once you
create a container from an image with `docker run` you can never change
any of the mounts (usually with `-v`) or port forwards or really
anything else. You can only change what is *in* the container, not what
resources it has access to. 

This is obviously for security reasons. But it can be really annoying
when you realize after the fact that, for example, you want to run
`docker` from within a container running with docker and need to mount
`/var/run/docker.sock` in order to do it.

The answer is to `docker commit` the image and rerun the new image.
Committing images regularly is probably a good idea during development
since you like want to snap your image back when you screw up and it is
the *only* way to do it. Like taking a backup of *all* of your work
within the container at the same time.
