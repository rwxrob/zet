# Jump forward and back in vim with `CTRL-O` and `CTRL-I`

Jumping back to previous position is a critical and often forgotten Vim skill. While it *is* a Vim-ism, it's an important one. The `CTRL-]` is discussed on the first `:h` page in Vim as is the `CTRL-O` to go to the previous position, but what isn't generally covered is that `CTRL-O` is also the way to return from a `gd` that jumps to the position a given symbol is defined in the source code. Using `CTRL-I` after returning allows toggling between the two location (ex: the definition of the thing and the use of the thing) very quickly.
