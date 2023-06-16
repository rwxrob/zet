# Remove line wrapping from .kube/config in .vimrc

```vim
au bufnewFile,bufRead $HOME/.kube/config set nowrap
```

