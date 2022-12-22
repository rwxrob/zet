# Footnotes *require* surrounding blank lines

> Each footnote should be separated from surrounding content (including other footnotes) by blank lines. (Pandoc Documentation)

At first I thought I was doing it wrong, then I realized that the footnote rendering engine in GitHub Pages is broken. It allows footnote references to be combined one after the other like reference links. But (as cited above) that is directly forbidden by the original footnote specification from which all the others should be derived. Glamour follows this convention as well as Pandoc since it is using Goldmark (which Hugo also uses).

::: Rant

The popularity of Goldmark just proves how low the fucking bar is. It's full of problems, but it the number one markdown package for Go these days.

:::

Glad I finally figured this one out. It's just as well, however, because footnotes tend to be long and hard to read when together. In KEGML there is no support for multiple lines within a footnote (for good reason). So that improves readability as well.
