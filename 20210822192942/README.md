# Pandoc Markdown is Out, Dollar Signs Non-Standard

Realizing now that default Pandoc Markdown is not compatible at all with
GitHub Flavored Markdown. Pandoc Markdown treats all dollar signs as the
beginning of a LaTeX math sequence. This is really too bad, because
while I support the need for math in zettelkasten notes, suddenly
imbuing dollar signs with more meaning causes them to all have to be
escaped in a way that is not only annoying to most writers, but
incompatible with GFM rendering making for very confusing things if read
from GitHub.

Consider the following title in GFM:

```
Use `echo "$(<"$path")"` Instead of `cat` in Bash
```

This has to be written like this in Pandoc Markdown:

```
Use `echo "\$(<"$path")"` Instead of `cat` in Bash
```

But the backslash shows up in the rendered title on GitHub, which can
really confuse people since that is even within a literal (backticks)
block. 

I'm sorry. I love Pandoc. But that's just fucked up.

So this means that I have settled on CommonMark + GFM Tables (which,
other than this shitty problem with `$`, is 100% Pandoc Markdown
compatible) for everything I do from now on. This means no math support
other than putting it into a code fence, as the R language does.

    #pandoc #bugs #commonmark #latex #markdown #writing #coding
