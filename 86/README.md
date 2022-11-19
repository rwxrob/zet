# Don't Care for `shopt -s autocd` But Cool

Just found out that some people use `autocd` which will change into a
directory automatically as if you had typed `cd` in front of it. But
this disables `CDPATH` and prevents tab completion of all the potential
directories from working. The only time I might be tempted to use it
would be on a system where I had to move around quickly and did not have
any of my dotfiles available. But in those cases typing `cd` with tab
completion is always way faster than `autocd` (unless I'm missing some
usage pattern that I was unable to uncover from quickly testing it out).
