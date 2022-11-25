# Still undecided on how much of Markdown list syntax to keep

Lists in Markdown have always been a freaking mess. I already know for sure that "long" lists will absolutely never be allowed in KEGML (officially). They cause to many problems and prevent one list from being close to another list without jumping through a bunch of hoops.

But, what about the whole soft-wrapping and multi-linen alignment thing?

I'm inclined to just drop all soft line returns at all, just like with paragraphs, so that every list item is one big line. This should dissuade people from misusing lists while allowing the rare exception of a list item that is really long.

```md
* Those asphalts are nothing more than jasons. Far from the truth, an edge can hardly be considered a tubeless diaphragm without also being a heaven. Unfortunately, that is wrong; on the contrary, a vaulted screw is a buffet of the mind.
  * Lasagnas are outdone italians. This could be, or perhaps the snowplows could be said to resemble unchewed childrens. They were lost without the deranged knight that composed their description. A samurai is an embowed guide. We can assume that any instance of a switch can be construed as a shickered stopsign.
    * An embowed texture's handicap comes with it the thought that the uncursed custard is a partner. Some brumal step-aunts are thought of simply as guitars. If this was somewhat unclear, we can assume that any instance of a foundation can be construed as an unhanged moon. Before families, thrones were only beliefs. A tomato is an unnamed light.
```

* Those asphalts are nothing more than jasons. Far from the truth, an edge can hardly be considered a tubeless diaphragm without also being a heaven. Unfortunately, that is wrong; on the contrary, a vaulted screw is a buffet of the mind.
  * Lasagnas are outdone italians. This could be, or perhaps the snowplows could be said to resemble unchewed childrens. They were lost without the deranged knight that composed their description. A samurai is an embowed guide. We can assume that any instance of a switch can be construed as a shickered stopsign.
    * An embowed texture's handicap comes with it the thought that the uncursed custard is a partner. Some brumal step-aunts are thought of simply as guitars. If this was somewhat unclear, we can assume that any instance of a foundation can be construed as an unhanged moon. Before families, thrones were only beliefs. A tomato is an unnamed light.
