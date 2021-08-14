# ZetEvents

A *ZetEvent* is just a line appended to the `$ZETDIR/.events` file which
the ZetDaemon watches by reading (`tail`) each line written to it. 

```
20210814180237676218983 C 20210814180316
```

The first column is the `isonan` nanosecond that the event occurred in
ZULU time. Size is 24 bytes, at least until the year after 9999.

The second column is the event type, just CRUD for now:

* `C` create
* `R` replace
* `U` update
* `D` delete

Other events will likely be added later, never will they be longer than
a single byte.

The third column is the unique zettel ID.

> 💬
> The hidden `.events` file will usually be added to `.gitignore` but
> doesn't necessarily have to be. You may elect to rotate the past files
> off in different ways to keep a running history of your interactions
> with your zettel repo.

Use the following commands to manage the events log(s):

* `zet daemon events rotate` to rotate the event log producing `$ZETDIR/.events-<isonan>`
* `zet daemon events delete` to delete the current log and start a new one

* [20210814174946](/20210814174946/) ZetDaemon
* [20210814180521](/20210814180521/) isonan When Your Need More Than isosec
* [CRUD](https://lite.duckduckgo.com/lite?kd=-1&kp=-1&q=CRUD)
