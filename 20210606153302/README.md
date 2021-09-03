# Keep Separate History in Each TMUX Pane/Window

At first you might be tempted to add something to your `PROMPT_COMMAND`
to force your history to update after every single command from every
one of your half dozen open TMUX windows and panes, but this is usually
a bad idea. It clutters the history causing you to have to do more work
than just look for the last command. It's better to leave them alone and
think of each as having a specific purpose, testing, for example, so
that all the history on that window/pane related to testing.

Sometimes there are worthy exceptions to this. For example, when
creating a challenge application (like I did for `skilbots`) that needs
to examine the history immediately because it is checking up on your
commands and giving you real-time feedback, or (like `skilbots`)
checking your history to give you pointers and catch problems in
real-time. Like having a `shellcheck` robot helping you out and letting
you know when things aren't optimal.
