# GitHub Flavored Markdown supports math

Realizing that default Pandoc Markdown is now compatible with GitHub Flavored Markdown. Pandoc Markdown treats all double dollar signs as the beginning of a LaTeX math sequence. GFM also has the `math` notation for fenced blocks, but Pandoc does not support it. So looks like using double-dollar sign is the way to go to achieve the highest degree of compatibility.

* Writing mathematical expressions - GitHub Docs  
  <https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions>
