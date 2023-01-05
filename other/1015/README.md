# Use `let mapleader=","` in Vim

I know it's a Vim only thing, but my gawd it is fast and easy to use. By
setting the `mapleader` you can quickly add mappings for any key combos
specific to your give file types:

```vimrc
let mapleader=","
au FileType go nmap <leader>m ilog.Print("made")<CR><ESC>
```

    #vim #tips #linux #unix
