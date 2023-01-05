# Realizing using `nodes` for everything is better than file system

In the first iteration of `keg` I just used the last modification time from the `README.md` file and added that to the `dex/nodex.tsv` file (before it became just the `nodes` file). This design has all kinds of flaws.

First of all, what happens when you copy the directory into another one? The next `index` command will get all the last modified times incorrect.

Then there's the idea that you can make changes to the file that have no substantial impact on the content and therefore should not trigger a change to the updated time stamp.

So, no more dependency on *anything* but the now mandatory `nodes` index file.
