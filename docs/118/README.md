# Announcement: Bonzai™ v0.1.1 is Released

It might still have some dependency resolutions or a quirk here or
there. But Bonzai™ version v0.1.1 looks officially ready for beta-ish
use. You can try it out using the template or my own `z` monolith.

```
go install github.com/rwxrob/foo@latest   // template
go install github.com/rwxrob/z@latest     // mine
```

I'm not that into alpha and beta releases (maybe I should start
given the potential scope of Bonzai). This release breaks every previous
Bonzai release in pretty substantial --- but important --- ways:

* **Main package move to `Z` and `bonzai/z`**

  This makes is far easier to build shell-replacing monoliths quickly
  and isolates the main code away from the module repo, which is getting
  a little more busy with other additions.

* **BonzaiMark™ support in `bonzai/help`**

  Yep, documentation is finally working again. This was the main hold up
  from a v0.1 release. It is safe to start broad experimentation over
  the next year or so before an official v1.0 (which I'll try to
  coincide with a conf talk someplace).

  Had to rework the [`scan.R`](https://github.com/rwxrob/scan)
  completely to get it finished, but help documentation is slightly
  better than before the port from `cmdbox` to `bonzai`. This included
  several re-usable additions to the other `to`, `fn`, `term`, and
  `struct` modules.

* **Other sections simplified as array of Section**

  This preserves the order set by the developer and makes writing them
  cleaner when reading the source while writing the documentation.

* **Prioritize shell script replacements**

  There are many reasons to consider Bonzai, but the priority use case
  going forward will be to replace collections of shell scripts. Design
  decisions going forward will always reflect this priority.

    #bonzai #release #golang #annoucement
