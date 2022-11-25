# GitHub supports advanced mathjax markup

Looks like GitHub has altered Pandoc and supports MathJax instead. This is good for users of the dollar sign, but it is still problematic. Better to just never combine a dollar on the same line as any math notation at all.

I especially like that you can use regular fences for math notation instead of the double dollar stuff. In fact, I'm dropping double dollar blocks entirely from KEGML since they are absolutely not needed (and never fucking were). Fenced (syntaxed) blocks have always been the way to go.

* Writing mathematical expressions - GitHub Docs  
  https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions
