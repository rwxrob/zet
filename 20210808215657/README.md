# Consolidating Zettelkasten and Zettel Casts (YouTube)

While seeking an opportunity to refactor all of my process of creating
and managing knowledge content I realized that the most fundamental unit
of knowledge that I work with is the zettel ("slip") and --- most
importantly --- that any video content I create worth recording is
also just an extension of a zettel, a zettel cast, which is a video
accompanying a zettel (the description of the video) with all the same
constraints (about 25 lines of 72-col text, under 10 minutes of video).

The only other video content I create is raw live streams (which may
eventually also have bookmarks into them). 

It follows, therefore, that all of this knowledge work should be
encapsulated within the main `zet` command (which may, one day, be a
subcommand of `kn`).

This conclusion has led to some other planned changes:

* Removal of any `yt` commands that have anything with `zet`
* Addition of `zet cast` command and subcommands
* Addition of `ZETCASTDIR` environment variable
* Dropping `$YOUTUBE_*` environment variables 
* Creation of `cast` API that any service command must match
* Addition of `ZETCASTCMD` environment variable
* Changing `yt` to match `cast` API and setting to `ZETCASTCMD`
* Putting off consolidation and event logging (for now)

A lot of this is driven by the eventually need to plugin other video
host provider services. Some people might want to use the system without
even using YouTube. Some might want to use Twitch hosting instead, or
Vimeo, or even GitHub itself.
