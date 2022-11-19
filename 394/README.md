# Install Vim Plug Plugin Manager in Vimrc

Here's a snippet for automatically installing the best Vim plugin
manager available currently:

```vim
" Install vim-plug if not already installed
if v:version >= 800 && executable('curl') && empty(glob('~/.vim/autoload/plug.vim'))
  silent !curl -fLo ~/.vim/autoload/plug.vim --create-dirs
      \ https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
  autocmd VimEnter * PlugInstall
endif
```

I've since removed the thing however, because it seriously opens up
security flaws when working with containers that run as root or putting
on internal machines that don't have Internet access. It was always just
a cute way to get around separate installation, but no one cares now
that everything is in a container --- especially with workspace
containers.
