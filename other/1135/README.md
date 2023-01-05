# `/tmp`<`/dev/shm`<`/run/shm` Virtual File System

TIL where the virtual file system that was once `/tmp` has gone off to.
It's currently `/run/shm` (which is usually a symlink to `/dev/shm`
now). I wasn't paying attention over the last decade and `/tmp` was
changed into a *real* file system some time ago in both Debian-based and
RedHat distros (as far as I can tell). Just today after auditing a
script that was writing directly to `/dev/shm` and thinking, "What the
fuck?! That the `/dev` tree!' I did some research and learned all of
the history about this change that I care to know. Suffice it to say,
many others thought encouraging anything to write directly to `/dev/shm`
for stuff that was once in `/tmp` is a fucking horrible idea. Hence, the
new `/run/shm` location.

I am actually quite pleased to realize this because my little `temp`
utility that makes me a temp directory into which I can scribble has
been filling my `/tmp` in a way that I actively have to address by
deleting them (eventually). All I have to do is start writing to
`/run/shm` and I'm golden. One reboot and they are all gone. Muhaha!
