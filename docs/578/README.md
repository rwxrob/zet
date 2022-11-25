# Just Realized Secure Shell Allows Deep/Secure KEG

I don't know why this incredibly obvious advantage didn't hit me
already. But since KEG is transport agnostic, and secure shell (`scp`
and `rsync` over `ssh`) are the preferred method, and since consumers
are the ones reading and rending on their end, that all you have to do
to lock down a KEG site is create a public key collection like GitHub
does. Just have people who you want to grant access send you their
public ssh keys and you just add them to the ssh config for the repo.
OpenSSH becomes your Web server replacement.

Oh my god, my head just exploded.

This would allow any number of Deep/Dark/Secure KEG subnets created by
any organization or community that wants with almost zero fucking effort
all secured with the best security in the world currently. The really
amazing thing about that is that the person running the secured KEG site
will know the exact number of people potentially using it and how much
based on their public key. All they have to do to shut down an abuser
who is pulling too frequently is remove the public key, or quarantine it
for a while. This is huge. This is the kind of thing I have to finish
and demo with a dozen or so and then present at DefCon/BlackHat.

    #keg #secops #deepweb #edtech
