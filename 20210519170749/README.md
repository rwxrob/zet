# Workspace Containers for Safe Shell Customization

One of the absolute greatest advantages of workspace containers is that
you can freely work on and test massive changes to things like `.bashrc`
without any impact whatsoever to your running system. 

In the past this has been bothersome because `exec bash` was not a true
test and anything else might make it so you couldn't login, or at least
not see much when you did. Now with workspace containers you can make
all the changes and just restart the container.

This is especially true of you use something like my `ws` workspace
management utility that mounts the home directory so that the files you
are work on persist between runs.
