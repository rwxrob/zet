# ZetDex: Flat-File Indexing That Just Works

ZetDex is the flat-file indexing system used for ZettelKasten repos.
Most files have an initial column that is the zettel isosec ID. (The
only exception to this is `changes`.) The `zet` utility has one command
for each of these index names. Files containing the latest output of
these commands live in the `$ZETDIR/dex/` directory. Running `zet
daemon` (in a separate TMUX window, in the background, or as a system
service) will automatically update these any time a change occurs and
optionally make any notifications needed.

* `changes`
* `titles`
* `tags`
* `videos`
* `figures`
* `refs`
* `links`

Block quote indexes are defined as the line number in any zettel where
an EmojiBlock occurs. The content of the block itself, however, is not
included in the index. The following EmojiBlocks are automatically
recognized.

* `ideas`
* `comments`
* `warnings`
* `rants`

Also see:

* [20210814155857](/20210814155857/) Flat-Files are Fine
* [20210502052620](/20210502052620/) Brilliance of isosec Unique Identifier
* [20210812165625](/20210812165625/) EmojiBlocks, CommonMark Blockquotes with Meaning
* Zet Command Line Utility (<https://github.com/rwxrob/cmd-zet>)

