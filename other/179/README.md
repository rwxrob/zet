# Burned by Shell Aliases, Again

I've written about this before, but aliases just fucking suck! I just
wasted five minutes figuring out why my `grep` from within Vim didn't
work (using `!!bash`). I was using UNIX philosophy at it's finest and
typed the following directly into my file under the references block of
my zettel.

```
zet titles | grep emojiblock | zet mark link
```

Normally, I would have expected this:

```
* [20210812165625](/20210812165625/) EmojiBlocks, CommonMark Blockquotes with Meaning
```

But instead I got nothing.

Why?

Because aliases fucking SUCK!

I added `grep -i` to get it to work. Then I immediately deleted *all* my
fucking aliases and replaced with one-line `exec` commands. Don't be me,
just say no to the `alias` command entirely.

* [20210813154054](/20210813154054/) ZettelMark: References List
* <https://rwx.gg/vimagic>
* [20210519200444](/20210519200444/) Why One-Line Scripts, Not Aliases or Functions
* [20210526152440](/20210526152440/) Always Create Aliases with Single Quotes

