# GitHub decided to stop giving search results

Thanks to lol_scraby I have the same thing working on sourcegraph.com, which is fine for now. Plus it has much better control over searching allowing anyone to alter the search. I don't know how often it indexes the content, but this is far better than GitHub arbitrarily dropping everything. It's also a hell-of-a-lot faster than GitHub's shitty search engine.

----

> It's our goal to remove these rules and index all code, but for now that's unfortunately the limitation.

Another arbitrary, invisible piece of shit decision from GitHub...

Today a user informed me that `!zetq` stopped working. When I tested it I discovered that GitHub search for my `zet` repo returns zero results every fucking time now, without any warning at all. I'm sure I've hit some invisible boundary at which they start refusing to index the content of a repo. I'm pretty pissed off. This means I have to accelerate the KEG indexing strategy and KEG Web rendering in order to get searchability back. The good news is that it will be way better than whatever everyone has now. I can also use IaaS so that I can make the primary search interface my Twitch IRC channel chat. The bot itself will do the searching and hand over a link to the public facing web pages. Then I just have to create automatic rendering and `rsync` when a change happens. This will get me by for now, until I can finish the rendering of the static search engine in the KEG Web site itself, which can be combined with Google searching as well. I'm thinking of adding a `robots.txt` to my zet though because I do *not* want that shit saved for time and all eternity (unless I say so).

* Code Search fails to search our private terraform repo · Discussion \#13919  
  <https://github.com/community/community/discussions/13919>
