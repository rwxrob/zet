# Personal logging in KEG/zet with hlog

Making written personal chronological log entries is something people have been doing since writing became cost-effective, and by different names: journaling, writing in your diary, or keeping a captain's log. Whether it be capturing the wincing pain of a teenage crush or the yield of an atomic explosion test humans have been keeping logs to make sense of life and track its events.

## I've always loved keeping a journal

I have long kept a journal. My mom got me started on it. I have stuff as far back as eight years old written down. Soon I started typing everything, just more fun I suppose. I do still love to use paper and a written journal, however. But the accessibility of my zet (KEG) has made it the logical choice for a place to add my notes. 

## Logs are for capturing moments in time

People forget that a log is primarily to capture a specific moment in time and the events, feelings, conclusions, and reactions at that moment. If something I want to write is time related, it probably belongs in a log entry and not a stand-alone zettel. Either way it is easily found and reorganized later if and when I forget and put too much into the log. I never want to get too over-analytical about what goes into a log entry to allow the writing to just flow. After all, that's the entire point of using the zettelkasten method in the first place. Save all the analysis and editing for later after the creative process of capturing the ideas has been done.

## Logs and dates help capture thinking at a point in time

Log entries also address another problem with a pure, timeless zettelkasten. It's easy to look at a zettel that pulls up in a search and wonder how long ago it was that I felt that way or wrote about that. Without log entries its virtually impossible to know when I had a particular thought. Often I will discover that a thought is no longer something I think and I want to update a zettel to reflect my new thoughts on a topic but don't want to lose the thought I originally had. This is one of the true benefits of a zettelkasten, the messy nature of dynamic thinking and discovery all captured in the same place. It is very valuable to realize what I *used* to think, when, and why I changed my line of thinking. By adding log entries I can have specific dated zettels but I can also add `hlog` time stamps to existing zettels as they are updated. I still don't think it is worth time stamping every single zettel. I will simply put a line `----` marking off the old zettel content from the level 2 (`##`) time stamp headings marking the update.

## Careful not to put too much into zet log entries

There is also a danger when adding logging to a zettelkasten that content that should go into a stand-alone zettel will end up in the log. While informally writing about that events of the day it becomes easy to dump a content into a single zettel that would actually be better as separate individual zet entries. I think the secret is to fire up a new zettel for such ideas or to refer to them minimally in order to keep the log a statement of events and conditions surrounding those events rather than the deeper ideas involved in the event.

## Added the hlog command for sorting

I added a `hlog` command script to my dot files to produce the following output:

```
# LOG20231003080243: Tuesday, October 3, 2023, 8:02:43AM EDT
```

This is intended to be the first line of a new entry. It will ensure that these entries always sort properly. Eventually, I'll add this as a command to `zet` itself. It is still within my strict design criteria of not adding anything to my `zet` system that could not be maintained by hand.
