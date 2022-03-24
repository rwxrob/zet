# Going to Make `lv`/`lva` Live Streamer Tool

Creating a Twitch Bot is a rather trivial process for most veteran
programmers. I've been just too lazy to do it. But after adding up all
these commands in a commands.yaml file it is about time to make it a
reality. Cloudbot is very amazing, but let's face it, there is a lot
more that I want to do with it not to mention integrate it with my
systems here to allow changing things on my system and activating robots
and lights and stuff at home.

All that fun stuff is good and all, but not being able to quickly create
a new information command is actually costing me time and money because
I just keep dumping stuff into Cloudbot never to be able to pull it out
through any API call or anything. The time to right a scrapper to get
all those commands is just about the time it would take to just fucking
make a Twitch bot in Go. Plus that gives me the opportunity to have it
connect to the IRC chat and bridge that as well as connect to all the
event API stuff.

And another thing: I keep adding new shell scripts to interact with
Twitch in different ways using `curl` commands but it would just be
better to send those events to a local queue and have the bot manage
them asynchronously, which could involve stuff besides Twitch as well.

I think I'll go with the name `lv` for the command line and `lva` for
the agent.

    #twitch #livestream #utility
