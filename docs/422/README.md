# Okay, Now I Feel Stupid, Vim-Tmux Now Linked

For ages (possibly eons) Vi users have been plagued by the disconnection
between the `screen` buffer and Vi registers. Well, apparently Vim users
have been enjoying this fix for many years. I finally gave in after
discovering this one in particular.

```vimscript
Plug 'roxma/vim-tmux-clipboard'
```

It needs the following added to `~/.tmux.conf` as well:

```
# form vim/tmux d/y buffer sync
set -g focus-events
```
