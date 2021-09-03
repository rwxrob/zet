# Fuck, `Ctrl-L` Works on BusyBox

Looks like BusyBox decided to use the default `set -o emac` mode on
their history, which really sucks. This includes clearing the screen
with `Ctrl-L` (which I truly abhor). I can at least throw that bone to
people insisting on not using `set -o vi` even though it makes complete
sense if everything else in your UNIX world uses `vi`.
