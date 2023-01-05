# Docker `exec` Interactive is *Not* a Login Shell

You probably want the following instead of just `exec bash`:

```
docker exec -it <container> bash -c "su - <user>"
```

Most people will never care that `exec -it` does *not* provide a login
shell. But if you ever want to create a working container image that you
commit regularly and use to create a consistent working environment then
you will *really* care about this difference. I've been burned by
forgetting this. There are a couple ways to check for this:

* `echo $0` will be `-bash` (the hyphen is the giveaway)
* `$USER` will be set

I discovered this because a login script that we use at work failed
because it was detecting `$USER` which wasn't there. Had that not
happened I would never have known that this isn't a *login* shell. There
certainly is *zero* documentation on that fact.

What's worse is that I missed this distinction before because I was
exec-ing in as `root` to set it up and `su - <user>` to get the user,
which *always* provides a login shell (that's what the `-` does).
