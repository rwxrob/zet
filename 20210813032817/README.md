# MimWorks `mim` Umbrella for `zet`, `yt`, etc.

I've loved the name `mim` and `mim.works` and have several of the
domains in my possession because I love it so much:

* `mim.sh`
* `mim.works`
* `mim.directory`

I've been seeking something that is worthy of them and I feel like `zet`
is getting there. In fact, so is `yt` and `post` and `twitch` and
`twitter`. MimWorks (or just Mim) will be the umbrella application for
all the others, each one modularly dealing with a different part of a
person's knowledge:

* `mim zet last`
* `mim zet cast`
* `mim post "Some new status."`
* `mim yt live`
* `mim open https://mim.works`

This allows the (eventual) creation of a CmdBox monolith with all the
composite pieces and plays better with users not looking to do massive
updates to their bash scripting environment. So far I think the
following utility modules would be good to support:

* `zet` - personal zettelkasten management
* `youtube` - YouTube API integration
* `twitch` - Twitch API integration
* `twitter` - Twitter API integration
* `iam` - personal state changes and notifications
* `work` - todo and personal task management
* `find` - personal search engine
* `follow` - follow other `mim` users or from `mim.sh` or `mim.directory`
* `parse` - parse PEGN expressions and grammars

By the way, this conclusion is one of the beneficial products of rapid
applications development and informal initial user testing on oneself.
This is the kind of thing I can get working as a proof of concept in
bash and then pitch to a community or sponsor as the basis for a Go
monolith application.
