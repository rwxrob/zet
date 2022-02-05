# Brilliance of `isosec` Unique Identifier

When I first was considering all the unique identifiers to pick from
today to compliment the ones Luhmann used for Zettelkasten, I wanted
something that could be created simply and done with pen and paper. The
current second was the right thing to pick. But then the question of
conflicting and changing time zones came up and the natural solution was
to use GMT/Zulu time. Within a single Zettelkasten it is guaranteed
never to conflict ever.

But the brilliance is in the shortness and ability to easily see when
things created with such ideas first came into being. You don't have to
look to hard to figure it out. On GitHub this means that
the most recent additions are closest to the `README.md` rendered content
near the bottom. It remains to be seen what happens when there are 10s
of thousands of zettels, but I'll deal with that when it comes up.

And `isosec` is also easy to create with just a calendar and a watch, no
dependency on a computer (like epoch has). I prefer to follow the path
of least possible tech required, "progressive design" from the web
world.

If you do have access to any UNIX or Linux shell you can simply use the
date command to generate it:

```sh
#!/bin/sh
exec date -u +%Y%m%d%H%M%S "$@"
```

Related:

* [20210810144945](/20210810144945/) Niklas Luhmann, Father of Zettelkasten
* [20210812144154](/20210812144154/) Zettelkasten Search Approaches

Tags:

    #uuids #isosec #scripting #unix #linux #bash
