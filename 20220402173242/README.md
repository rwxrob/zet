# Need to Port Vi from BusyBox to Go: `vigo`

All this fighting about how much NeoVim is shit has got us playing with
the idea of writing an entire version of Vim (starting with `vi` from
BusyBox) in Go and call in `vigo`. I'm sure someone is already working
on it (yep, just found one) and has probably already snagged the name,
but maybe not. All I need are the essentials anyway, promoting a UNIX
philosophy, even within a monolith, makes sense.

This one uses `termbox`, which I have coded in (skilbots) but I would
want to build it off of `tcell` instead. One day this will get done,
just probably after I finish all of Bonzai, PEGN, and KEG.

* <https://pkg.go.dev/github.com/thundergroove/vigo>
