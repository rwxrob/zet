# Get Hugo to see README.md instead of (the stupid) `_index.md`

Hugo is so fucking brain dead on so many things. This is one of them. The entire fucking world uses README.md as the `index.html` alternative in Markdown. But for some FUCKING STUPID reason, Hugo decided to do its own completely different thing.

The "solutions" include creating symbolic links, but those don't work on all operating systems and `git` makes no promises about how to deal with them.

* How can I convert markdown files contains relative link with end with \*.md to hugo links? - support - HUGO  
  <https://discourse.gohugo.io/t/how-can-i-convert-markdown-files-contains-relative-link-with-end-with-md-to-hugo-links/42087>
