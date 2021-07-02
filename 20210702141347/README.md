# Kubernetes Efficiencies Lost to Putty on Windows

> "sure you can come be a carpenter, here's your spoon" @mousepotato

Kubernetes and cloud-native are about driving efficiencies in an
organization, particularly for "developer productivity" (which includes
SREs these days). But those efficiencies are entirely lost if your
organization demands that your IT team only use Windows with Putty.

Companies approve millions for Kubernetes and yet don't even have an
official Linux laptop workstation image for their employees. If you
don't see the irony in that, well, you have bigger problems.
Cloud-native transformation starts by getting your IT team the tools
*they* need before rebuilding your IT tech stack to include "cloud
native" and "DevOps". 

Windows with Putty connecting to servers to do all your development is a
server-dependent paradigm that died more than 15 years ago. How the hell
is your team supposed to work without an Internet connection? (This is
also the main problem with all the web-based pair programming and
developer tools.) You have defeated the entire point of Git by forcing a
remote login to do *any* development. This is the polar opposite of
DevOps, which fundamentally depends on Git.

Please tell me you see how stupid this is. If not, well... just don't
utter words like this:

"I just don't see why you need Linux? Everyone else is doing just fine
without it. We need to figure out what you are doing differently and
decide as a team what to do. Did you get that Helm chart finished?"

It's 2021 for God's sake.

Stop and think, why has Microsoft invested so heavily in WSL2 and Linux?
Since 2014 MS has been diligently focused on integrating Linux at the OS
level. The "developers, developers, developers" company that once called
Linux "viral" and never to be trusted saw the writing on the wall, fired
those people, and get busy getting developers their Linux they demand.

Developers use Linux. But not just them. The entire IT world is based on
Linux these days. Containers could not exist without `cgroups` that
Linux brought to popularity. It follows then that any company's *top IT priority* is
getting your people 100% trained and using Linux as their daily driver.
Punishing these developers for even asking the question, or making them
feel small for questioning the official Putty on Windows position is a sure
guarantee to get them to walk out the door, and in the current drought
for skills cloud-native, Linux professionals that could literally kill
your company.

## "I'll Quit Before I Use Putty"

I've caught myself saying those words three times now on my new team. It
comes off as a joke, but I'm very serious. If your company and team is
so completely unable to realize how fucking stupid using Putty on an
official HPC Kubernetes team is then I simply want no part of it. If I'm
the only one on the team who actively uses TMUX and screen then I
already have an uphill battle. But, I can get equal or better pay from
someplace else. 

Even Microsoft has official tools for this now (WSL2 still has
annoyances.) At least distribute IT images with WSL2 properly installed
and configured to begin with (even though, as my friend suggests, "you
just gave the carpenter a knife instead of a spoon" with which a lot of
junior carpenters might kill themselves or someone else). Or better yet,
create a solid Linux workstation image like so many do already and only
give it to people you *know* can use Linux.

## Cowboys Will Create False Perceptions

If you are a manager, you probably have cowboys in your team already
that you don't even know about that appear to be doing the same tasks as
the rest of the team without any regard for IT policies at all. This is
just cheating. They've already installed their own Linux distribution
and fooled everyone because they haven't been caught, or worse, they've
turned that little Windows laptop into a full SOCKS proxy router and do
all their work on their personal machines using the laptop as their own
personal VPN gateway into your network. Such cowboys should be fired
immediately. They place the entire organization at risk because their
hubris doesn't allow them to see the danger they've exposed the company
to. Of course, they never see it that way because their arrogance has
convinced them that they are invincible. They're not.

If you are the cowboy, you are hurting everyone else on the team because
you are creating a false perception that "everyone else is doing this
just fine" when they really are not. So all the new people look like
idiots compared to you because they just want to following the IT policy
rules and are forced to use Putty on Windows, for example. Besides, you
might not be afraid of being fired. You might thing that you can get a
job anywhere. But if you get fired for "cause" because you opening
violated basic security policies that shit will follow you. Stop now.
Have the courage to stick up for *everyone* who is suffering. If you are
really that good, then walk out into another job that will allow you to
do such things and trust your skills. At least everyone else won't pay
the price while you are there.

## "Conservatives" Will Claim You Don't Need It

When I was at IBM I came onto a team who had all their critical source
code in tar balls, that was it. 1000s of lines of code in nothing but
tar ball backups. No source management to be seen anywhere. I had to
setup Subversion on my own as an "experiment" (approved, btw) and
eventually everyone adopted it. But had I put that to a vote it would
have failed instantly. 

"We don't really need that, do we. We've been just fine"

IT conservatism is one of the biggest demotivators anyone can
experience. It's hard to balance this versus what is trending, but
things like `git` are *not* trends at this point. People asking to
install NeoVim (alpha software shit) on production systems *should* be
laughed out of the room.

People are plenty happy to connect to systems with only
Vim 7.+ installed, no `screen` or `tmux`, and back level versions of
just about everything else, oh and no `docker` installation at all to
speak of. Usually such teams might not even know what `git` is or how to
use it responsibly to store everything in source management. But when
they say, "just use this and such" and your `.vimrc` breaks because you
are expecting to at least have version 8+ you have to start responding,
"what the fuck are you talking about" (while you prepare your CV for a
job change).

In fact, in some places to run Docker Desktop on your computer you have
to get special permission to have admin rights and manage the
installation yourself, even when DD decides to ship with a [fatal
error], but who knows, it could have been the forced Windows upgrade
that happened at the same time, which happened during some critical PD
work, by the way.

[fatal error]: 20210702142020

## Zero Trust to the Rescue

I happen to think there is a new dawn and it's called "zero trust". It
is a new IT paradigm that doesn't trust any device whatsoever that is
connected to the network. Let's face it, anyone truly motivated can
easily get on your corporate VPN, particularly if you have 20,000
employees all over the globe. Creating an IT atmosphere where you expect
every single system to levels of security that could withstand direct
attack from the Internet is *not* overkill. It's the new normal.

This is why so many cloud service providers are getting so popular now
and services like GitHub Enterprise, Slack, MS Teams, and other
cloud-based solutions are becoming normal. The more IT departments take
the zero trust position, the more they can expose entire segments of
what would be an internal intranet to the actual Internet.

BYOD then becomes possible because you automatically assume that any
device in your entire infrastructure has been compromised. This includes
all your IT team's personal laptops and phones. So you create
expectations on them.

There are organizations that will *never* go for this, that demand air
gaps even between their network and the outside world. Even if one USB
stick would blow it all away (remember Stuxnet). But at least adding a
level of trust to the IT team would allow them to get work done using
the tools they know and love..

## Ranting Helps, But ...

All this ranting makes me feel better, but it isn't the kind of thing
you can say directly to the decision makers. They'll just get offended,
or puff up because their ego and pride have been bruised --- especially
if you are a noob like me who still has a lot of Kubernetes to learn.
But I feel fine knowing that my knowledge of just about everything else
in the "developer productivity" area destroys theirs even though the
might be able to talk the Kubernetes stuff. I've never felt more
motivated to help people get a *solid* base in the tools they will use
every day *before* launching off into cloud native land.

I also really like being around these human beings. They are phenomenal
people, but at the end of the day, I'm having to decide if I want to
continue to remain with them and suffer by being forced to use Windows
every day, and eventually dying from a heart attack from all the
cortisol it pushes into my system, or just walk away and find another
group of amazing people that will actually let me run Linux on my
workstation, every fucking day.
