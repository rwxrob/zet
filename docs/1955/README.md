# Creating `mim` as my bot to ask questions of from anywhere

Was going to call it `pub` but my DNS name for `mim` still exists and Mimir is the Norse god of knowledge. Someone else already used the name out on the internet somewhere, but who cares. I'll create some bullshit acronym to go with it. The `pub` command can stay for creating published content, like static site generation and such. I've thought of bringing back `cava` as well, the architecture of `cava` is sound and it divides the work into two components, a **conversational assistant** and **virtual agent**. For now, however, `mim` will just be a chat bot on steroids that depends on `rwxrob/keg-go` package. In fact, `cava` and `skeeziks` and `mim` are all ideas that sort of predate the latest `keg`/`zet` iteration, so they can be built into `keg` itself. I already have very powerful PCRE `grep` ability built into it.

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
