# Getting the Width and Height of An Image from CLI

The ImageMagick application, included in almost every desktop Linux
distribution, comes with the `identify` command line tool to detect the
height and width in order to create a standard ZettelMark figure name.

```bash
#!/bin/bash

figname() {
  # TODO check for existence of identify
  local w h file suf
  file=${1##*/}
  suf=${file##*.}
  w=$(identify -format "%w" "$1")
  h=$(identify -format "%h" "$1")
  printf "fig-%sx%s.%s" "$w" "$h" "$suf"
}

figname "$@"

```

Related:

* [20210813202844](/20210813202844/) ZettelMark: Raster Image Figures
* [20210830172929](/20210830172929/) Figure: Typical Kill Chain
* [20210830175443](/20210830175443/) Prefix 'Figure:' Required for Figure Zettels

Tags:

    #images #bash #scripting #cli #tips #zettelmark
