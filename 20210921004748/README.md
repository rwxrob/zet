# Use `if has("eval")` for `vim-tiny` Detection

The `vim-tiny` that comes on most container distros does not have many
of the things most people have enabled in their `.vimrc` file. To get
around all the errors and still be able to use your same `.vimrc` file
everywhere (which you can easily copy with `git` or `k cp ...`) add
conditional checks around anything that produces an error only when
running `vim-tiny`.

Related:

* <https:github.com/rwxrob/dot>

Tags:

    #vimscript #tips #vim #vimrc
