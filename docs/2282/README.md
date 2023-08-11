# Go documentation format has been updated to be markdown-ish

I guess I missed this stuff in the release notes. Notably, headings are now marked off with hash tags (`# heading`) like markdown. I noticed this when my Go formatter automatically detected it and forced it to be there. Apparently, this was added in 1.19.

Also, indentation can be a single tab instead of four spaces as before.

And I *love* that clean reference links have been added:

```markdown
Here is [skilstak] link.

[skilstak]: https://skilstak.io
```

* Go Doc Comments - The Go Programming Language  
  <https://go.dev/doc/comment>
