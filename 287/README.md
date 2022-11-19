# Markdown Reference Links

Reference links are links that come later in the Markdown document. Even
though they force the entire Markdown document to be parsed in order to
render the link that needs it (putting a huge burden on *any* Markdown
parser) they are worth it because of the readability they provide.

```markdown
I am on [Twitch] if you want to bother me (or be bothered).

[link]: <https://twitch.tv/rwxrob>
```

This readability carries over even if that Markdown is written on paper,
which you should do as a part of the [Zettelkasten Method]. In fact,
this zettel contains a rather long link to search for all references of
the ZK method:

```markdown
... a part of the [Zettelkasten Method]. In fact, ...

[Zettelkasten Method]: <https://github.com/rwxrob/zet/search?q=zettelkasten>
```

> By the way, watch out for automatic line wrapping since they should be
on the same line.

[Zettelkasten Method]: <https://github.com/rwxrob/zet/search?q=zettelkasten>
