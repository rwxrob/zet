# Use `yes | unminimize` to Inflate a Container

Sometimes you want the whole thing. Using `yes | unminimize` will first
call `apt-get update -y` and then install man pages (but not `man-db`
for some odd reason).

Note that you probably want a `apt-get upgrade` as well to make sure you
have the latest version of that operating system.
