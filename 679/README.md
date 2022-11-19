# Eliminate Soft Returns from Markdown

In 2022, Markdown no longer needs soft returns in paragraphs (and hasn't for a while). They've always been controversial, and for the most point people have just been annoyed by them or by not having them.

Those who are annoyed *because* of them hate that lines wrap unnecessarily and at highly unpredictable column numbers. Some wrap at 80, others at 72, others at 108. The wrappers cannot decide what to use for their wrapping unless they are writing IETF RCS (which is 72, btw).

Those who are annoyed *without them* hate that they have to navigate huge lines in ways they have not yet become accustom to in their text editor of choice (usually not ones that use a mouse). Beginning vim users in particular can be annoyed at being required to actually learn vim navigation instead of just spamming navigation (hjkl) keys.

Neither of these camps really has enough of an argument to convince the other that their is the best, until they start to consider source management applications and simple tools like `diff`.

Consider the following with a soft wrap.

```
This is all semantically
the same thing even though on two lines.
```

This is all semantically
the same thing even though on two lines.

Now we have the exact same thing wrapped differently.

```
This is all semantically the same thing even though on two lines.
```

This is all semantically the same thing even though on two lines.

Right away you notice that the second reads better than the first since your editor is doing the automatic wrapping for you.

Let's move a few words from the second line to the first and add a word, then
check out what `diff` reports, but you can probably guess.

```diff
1,2c1,2
< This is all semantically
< the same thing even though on two lines.
---
> This is all semantically identical
> even though on two lines.
```

The second line was changed, but not in a way that is significant.

When using a single long line we see that only a single line was changed, but there is nothing in `diff` to indicate what on that line changed. This drives the old-school wrappers crazy. Considering how long an entire paragraph might be, that can make for some very hard to debug content.

```out
1c1
< This is all semantically the same thing even though on two lines.
---
> This is all semantically identical even though on two lines.

```

But the reality is, looking at these differences using `git diff` or any other modern tool (including GitHub commit history) will show the specific word that was changed.

Now consider that all modern editors, including `vi` in `tmux` or `screen` support autowrapping to the width of the pane or window. This gives authors control of how much of that paragraph/line they actually want to see. It allows them to browse a file in a tiny pane in the upper corner of their screen without it getting *seriously* messed up with random soft wrapping.

Ironically, I have known this for years and forced myself to go back to 72 column wrapping in 2021 when I started my latest zettelkasten repo. I must say, it is one of the decisions I most regret now (the other was forcing an isosec name for all the node directories instead of pulling it from a mandatory title for each zettel node). So, I'm going back to disabled line wrapping and already it has saved me a ton of wasted keystrokes rewrapping paragraphs unnecessarily. What was I thinking!
