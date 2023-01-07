# Personal publishing platform (`pub`)

The `pub` is the second half of `keg.pub`.

Once upon a time I called this `live`, a way to manage all the ways that a person might want to "go live" on social media and streaming platforms. But now I realize it is part of a bigger suite of applications involving self-publishing in all forms of media, primarily written content. I've realized that written content is still king.

* It can be searched
* It is easy to alter and maintain
* It underlies all other content
* It is more shareable

It is super important that written content be considered fluid and changing. The current abysmal state of the Web is largely because so many have forgotten this core fact (to Tim Berners Lee's great chagrin).

So `pub` will be a single application that contains ways to publish content to everything there is out there in a modular way. This includes the regular big services:

* KEG
* GitHub
* YouTube
* Twitch
* Mastodon
* Twitter

It will take a really long time to get `pub` anywhere near done, but it's the long term goal after the other main Go projects of 2023 are done.

***Enable direct chat/cli user interface to any keg.***

Users retrieve information from a keg by sending commands or queries: 

* Commands always begin with an exclamation point
* Queries always begin with a question mark
* Commands map to keg nodes that have a title with the command in it
* Queries can be keywords, PEGN, or PCRE regular expressions
* Queries can be scoped

***Query scopes***

* title - first line (always <=70 bytes)
* summary - first 400 bytes of first paragraph
* para - any paragraph
* list - either numbered or bulleted
* numbered - numbered list item
* bulleted - bulleted list item
* fenced - within any or specific fenced block type
* math - within any math block
* lede - any lede sentence
* beacon - any beacon span in title, para, or list
* inflect - any inflect span in title, para, or list
* div - within any or specific div fenced block type
* figure - alt text of a figure
* foot - text within a footnote

***Service specifics***

* Twitter/Mastodon/IRC/Discord/Slack - only respond to direct messages unless special "room"
* Twitch - always respond in public chat with limits
