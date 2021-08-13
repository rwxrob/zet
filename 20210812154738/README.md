# ZettelMark, EzMark + Video and Tags Lines

ZettelMark is EzMark (essentially simplified CommonMark with GFM tables)
with the following semantic additions

## Video Line

```markdown
# First Line Title, Followed by Blank Line

📺 <https://youtu.be/<id>

First paragraph starts here ...
```

* Must be third line beginning with television emoji (📺)
* Must have one space following emoji, then URL with `<>`
* Must be followed by blank line
## Zettel Links

While encouraging the reader to use a browser that will allow searching
of *any* word that appears in a zettel, sometimes it remains a good idea
to provide a direct link to a specific zettel.

* Use the `isosec` zettel ID wrapped in slashes (`/`)
* Keep links inline when included (no ref links for zettels)

```markdown
[EmojiBlocks](/20210812165625/) are nice to keep things easy.
```

This is a technique which can be done by hand (actually on paper) when
needed.

