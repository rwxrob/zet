# Don't Fix It, Burn It

Been approaching cloud-native architecture with a dated mental model.
Rather the fixing and pampering servers, I should be burning them and
replacing with better ones. Let me explain.

Back in the day you cherished every one of your precious servers that
you loved and cared for making sure it had all its needs met and was
well protected from unauthorized changes. You sweat blood day and night
to keep it pristine and wonderful, to be up 99.99% of the time. After
all your livelihood literally depended on that exact number ("4-nines
uptime"). 

When your system needed a fix or a change you went through hoops to make
sure the changes were solid because recovering from my system changes,
even a simple patch was nearly impossible. Instead, another patch or fix
would be applied to fix the first one that broke the system, when
possible.

But all that has changed.

In the age of "golden images" and "ephemeral containers" you just
maintain the image (away from production) and essentially throw away
your old servers ("burning" them) and replace them with new shiny
virtual ones. Instead of patching, we replace the whole fucking thing.

There are caveats. Did you have something on that "node" (we don't even
call then "servers" anymore) that was not persisted to network storage
or a Git repo? Sucks to be you. This is the new world of disposable
servers, where the server gets no love, where the Windows "just reboot
it" school of system operations has come to dominate the industry
thinking of our time. There is so little love for our beloved servers
today that some have even taken up the completely false moniker
"#serverless" asserting that there, is, in fact, no *real* server at
all. How dare you?! ;)

It's not bad, just different.

When I saw `/var/log/messages` trashing this shit out of a "node" my
knee-jerk reaction was to do whatever was in my power to stop it
immediately. "How dare that application abuse my logs?!" was my BOFH
thought. 

But my concern was met with what amounted to "meh" from the more
cloud-native-ey people on the team. "Who cares? Been that way for ages.
Let's check the latest image and see if its fixed." Then, when
they were not, tweaks to the image would be created and "pushed"
eventually, usually without even a change management window. "Oh my
fucking God!" I thought.

> So because thou art lukewarm, and neither hot nor cold, I will spew
> thee out of my mouth. (Revelations 3:16)

The angry white guy in the sky wants commitment, one way or the other.
And you can be damn sure this applies to cloud-native deployments as
well. When approaching "server management" (which isn't even a term
people use anymore preferring "infrastructure management" instead) all
of this brings out the problems with hybrid thinking about those
"machines". If you attempt to approach things both from the old way and
the new, well, you could get spewed out of God's mouth.

For example, `/var/log/messages` is *not* on NAS (thank God), it is not
persistent, and it is too much to send to ElasticSearch or some
cloud-friendly logging system. In some cases writing them all to a
central `syslog` server (way ahead of its time) is still a good idea.
But the point is that there is this nebulous space on these "nodes"
where stuff exists (the host operating system) that is outside the scope
of the Kubernetes stuff. When stuff on the "host OS" breaks (like
Kubernetes fucking up because of NAS latency and dumping four log
messages a second about "orphan pods" to logs) you are stuck with
very little recourse. 

You cannot easily write a script to fix them all with Fabric or `ssh` or
something. There isn't an agent on them because that is Kubernetes job.
And they are practically impossible to get to because of all the fucking
around with networking that the "cluster" does. To even get to the
things you have to create "head nodes" that have `ssh` access and then
proxy or tunnel even to log into the fucking "nodes" that need fixing.
What would have been one hour of work to write a script that
concurrently tails all the logs of every server now requires deploying
an administrative Job or Deployment that uses the head nodes to get at
the logs and is all completely dependent on Kubernetes working as it is
supposed to.

And it probably isn't even your job.

The age old conflict between developer and operator portrayed so well in
Silicon Valley with Dinesh and Gilfoyle exists between the
SRE/Infrastructure team supporting the server/node and you, the
cloud-native person who's big-fucking application is not working on the
hosting hardware provided. So you end up in polite calls where the
"operations" people talk about why the logs are full while the
"applications"/Kubernetes people explain how it is out of their control.
As a morbid twist of good fortune there aren't many "operations" people
left to complain, and even less to complain about now that the
"machines" they call "nodes" aren't even real either. They just tweak
the image and schedule a new deployment date. Done. Fixed.

No wonder IBM bought RedHat.

Why? 

Because IBM "Think Big" (read: "everything looks like a mainframe") which is why they bought OpenShift.

Why?

Because OpenShift thinks big. It wants to control everything and likes
things like `systemd` (let's all just accept it won and isn't all bad).
But more importantly OpenShift bought CoreOS.

Why?

So that there *is* no more server. There is only Zuul, oh wait, BORG,
hum, I mean, Kubernetes! 

With CoreOS servers are not only just "nodes" but run an OS that
practically doesn't work without connecting to the cluster (yes, I know
you can, but it is seriously frowned upon). Accounts are not even
created on these OSes. The k3os takes the same approach, but for smaller
stuff. And RancherOS is *literally* just a bunch of containers. Even
`systemd` is in a container.

Yes, cloud-native operating systems today are little more than internal
parts of the main Kubernetes "OS" per se. Adding nodes equates to just
adding cores and memory to a larger (pardon the term) *distributed
mainframe*. After all, that's what we have reached. If "Kubnernetes is
the new OS" then all these servers are just node devices in the
monstrous, invisible case that encloses the distributed hardware of
a single logical system of orchestration and operations, an OS.

What did we do when a RAID 5 disk went bad? Pull it out, replace it,
then go to lunch, of course. Back then hardware admins would wince in
pain at the cavalier attitude we had with what they had come to love and
respect, those wonderful hardware devices that they would dutifully
defrag and protect from degaussing, heat, and such. How dare we treat disk
drives without the respect they deserve? 

Yeah, that's where we are with servers themselves, sorry "nodes".

By the way, I'm not complaining. I use this "just burn it" approach
already with my Linux workspace container. As I discover new things I
iteratively add and change the Dockerfile and image, and can pull it
down from anywhere and use my new and improved OS/distro. It's much
faster than having to reconfigure an *actual* machine, or even a virtual
machine for that matter. Change, build, push, pull and I'm working with
the changes. Then just "reboot" to get the fixes. Distro hoppers freak
the fuck out when I do that. Oh well.

Who knew Microsoft was right about the "just reboot it" approach
to operations this entire time. To be fair, that was my virus management
strategy as well. Give my 9-year-old boy full admin access to his
Windows machine and just burn it and reinstall everything ever month. So
thank you Microsoft for showing us that we can just burn it and built a
new one, instead of laboring over maintaining the current one we have.
