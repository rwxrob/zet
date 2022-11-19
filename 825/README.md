# Samba Still Sucks, Often `sshfs` is Just Enough

If you've never had to fight with all the shit involved with getting a
`cifs` mount to actually work, or `smblient` to do what you want you
might be better off just mounting anywhere you like with the simple and
easy `sshfs` instead. Obviously, you have to have `ssh` access to the
same stuff that is being mounted, but this is often the case in a
production enterprise environment. Hell, you might even be doing it more
securely than Samba depending on how it has been setup. And the best
part of all is that you can use `sshfs` *anywhere* that you have `ssh`
access without fucking around with anything else related to network
mounting. This is the bliss most of us are seeking just to keep working.
