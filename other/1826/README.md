# Remap k to gk and j to gj for better navigation in Markdown

This makes it easier to navigate those long single lines (which are preferable over wrapped lines in 2023 because they fit into any pane size and wrap properly).

```vim
au FileType markdown,pandoc noremap j gj
au FileType markdown,pandoc noremap k gk
```
