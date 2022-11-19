# Get Last Lynx Bookmarks as Bullets in Vim

Here's a quick script to grab the last bookmarks from Lynx and inject
them into your Vim session with `:lynxa 4` (or whatever). This way you
can do lightning fast research and dump them all into a zet (instead of
some bookmarks file you will eventually lose and not ever be able to
search effectively.

```bash
#!/usr/bin/bash

count=1
if test -n "$1"; then
    count="$1"
fi

IFS=$'\n'
html=(`tail -"${count}" ~/.lynx_bookmarks.html | pandoc -f html -t markdown --wrap=none`)

for line in ${html[@]}; do
    printf "* $line\n"
done
```
