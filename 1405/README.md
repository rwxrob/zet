# TMUX Esc Breaks Vim on Windows

I kept typing accent characters instead of having the characters
navigate. Then I realized it was because of ancient terminal emulation
that used to wait around for more characters after the escape character.
No one needs this today and it will just really fuck up your vi sessions
if you don't have the following:

```tmux
set -sg escape-time 0
```

* shell - What\'s the effect of \`escape-time\` in Tmux? - Unix & Linux Stack Exchange  
  <https://unix.stackexchange.com/questions/608142/whats-the-effect-of-escape-time-in-tmux>
* <https://github.com/mhinz/vim-galore>
