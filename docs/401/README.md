# Immediate Bash History Updates for All Panes

This little snippet will force all your TMUX panes running Bash shells
to have their histories synchronized (even though I prefer each to have
its own history).

```sh
PROMPT_COMMAND="${PROMPT_COMMAND:+PROMPT_COMMAND;}history -a; history -c; history -r;"
```
