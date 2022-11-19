# Use `sshpass` When You Must Use `ssh` Passwords

Unfortunately, there are a lot of situations where using a secure key
just isn't enough. Usually a stupid organization that you are involved
with doesn't allow for any of the usual options and *forces* you to use
a password to authenticate (as fucking stupid and insecure as that is).
I happen to be involved with one that will not accept anything but a
password and that also happens to force a remote `ssh` connection to be
terminated every 10 minutes or so. But `sshpass` just might be the
thing. It allows you to replace all your `ssh` calls with ones that
refer to passwords that have been semi-safely stored in files. (Sorry,
for this stuff there is just no getting around that.) And for God's Sake
do *not* put that stuff into your command line history and environment
variables.
