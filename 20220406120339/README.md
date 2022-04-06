# Announcement: Bonzai™ v0.1.0 is Released

It might still have some dependency resolutions or a quirk here or
there. But Bonzai™ version v0.1.0 looks officially ready for beta-ish
use. I'm not that into alpha and beta releases (maybe I should start
given the potential scope of Bonzai). This release breaks every previous
Bonzai release in pretty substantial --- but important --- ways:

* **Main package move to `Z` and `bonzai/z`**

  This makes is far easier to build shell-replacing monoliths quickly
  and isolates the main code away from the module repo, which is getting
  a little more busy with other additions.

* **BonzaiMark™ minimal support in `bonzai/help`**

  Had to rework the [`scan.R`](https://github.com/rwxrob/scan)
  completely to get it finished, but help documentation is slightly
  better than before the port from `cmdbox` to `bonzai`. This included
  several re-usable additions to the other `to`, `fn`, `term`, and
  `struct` modules.

* **Other sections simplified as array of Section**

  This preserves the order set by the developer and makes writing them
  cleaner when reading the source while writing the documentation.


    #bonzai #release #golang #annoucement
