# End and Exit Shell Scripts with `exec` Whenever You Can

The `exec` allows the command and arguments passed to it to take the
space and process ID and signals receivers of the currently running
script effectively swapping the script out for what is called. This is
almost always better than calling it as a subprocess and waiting for it
to finish. For example, the PID, environment variables, signal handlers,
and any associated background jobs all remain. It is exactly the same as
if the executed command were run instead of the script calling it.

One example of this is anything with `tmux` that needs to be running in
the current shell, window, and pane.

