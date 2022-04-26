# My Top Priorities for Boost

The top priorities are (unsurprisingly) in line with RWX (read/research,
write, and exchange/explore/experiment).

**Bonzai™ Monolith Command Compositor** - Thank god this is 90% done, but
I need to make sure it *stays* done and I don't rip the shit out of it
for some stupid reason. Everything else I ever make will have a very
critical dependency on Bonzai. It's the reason I spent most of the
Winter working on nothing else. All our Go coding in Boost will be in
the form of Bonzai trees.

**Info commands utility (`info`)** - I have to be able to quickly audit
which commands haven't been finished yet so that I can just write and
fill them in as I can. The graph node method of writing is very
effective, but faces a challenge in leaving nodes that are not fleshed
out because you just make a placeholder for it and come back to it
later. This could be the most important edtech tool I ever write, even
more important than my Zettelkasten stuff. This could relate to the
`z agent` stuff as well to communicate with Twitch instead of Cloudbot.

**Zettelkasten PKG note taking tool (`zet`)** - Helping people get into the
habit of RWX will require help. While it is true that writing your own
knowledge management system is a good coding exercise, people will need
something right away to begin using to take notes in a way that is
consistent. The Boost is one golden opportunity to get people to
participate in KEG.

**Knowledge Exchange Grid (`keg`) tool** - Second only to digesting
knowledge, and writing it, is exchanging it and exploring. This is what
KEG is all about. There is a lot more to KEG than sharing Zettelkasten
repos, but it's a start. I really need to get that part of it done,
which includes rendering as HTML and publishing in a consistent way on
the Web (for now).

**Fluff for "happy little local clouds" (`fluff`)** - The biggest pain
point when setting up a local lab is setting up and tearing down local
VMs using the workstation you are on. That is why `fluff` was conceived
and it is needed. It's a big part of the X in RWX, a place to experiment
and blow shit up safely.

**SKILSTAK Learning Bot (`skilbot`)** - Something I finished years ago,
but now that Bonzai is ready, I need to redo it in `tview` and start
creating Bonzai branches that encapsulate specific tasks and lessons.
The `skilbot` learning method focuses on putting the bot near the
learner rather than forcing the learner to go on the Web for something.
The bot then watches what the learner does on that system and acts like
a proxy standing in for a mentor during development and task repetition
for learning. The learner can optionally allow the telemetry to be sent
to the mentor for consideration and advice. (Yeah, telemetry for good
this time, for fuck's sake.) The Bonzai modularity is going to make
`skilbot` get around all the problems with dynamic composition before.
But it will be based on the assumption that anyone using one be
eventually able to compile their own.

    #boost #todo #tools
