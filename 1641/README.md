# Use `pathprepend ./` for Faster Dev Iterations

Once you have a `pathprepend` function in your main `.bashrc` you can
use it to easily add the current directory `./` while working intensely
on a specific development project. This will save you from moving
your executables someplace else to get them to run. Later, when you
exit this shell (or TMUX window/pane) the alteration to the `PATH` will
be deleted as well without any permanently insecure changes to it.
(Never add `./` to your *actual* `PATH`, of course.).
