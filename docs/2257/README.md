# Review of www.shellscript.sh

I love when people attempt to help others. But so often the content is so wrong (or old) that it does more harm than good. For the most part <https://www.shellscript.sh> gets most things right, but here are some very glaring omissions, enough omissions, in fact, to make it something I would strongly discourage anyone from looking at *at all* because of the bad habits it might instill.

## Never, ever add suffixes to your shell scripts

This prevents them from being replaced with other code later. Besides, it is definitely *not* following the UNIX philosophy (which the author makes a rather big deal about at the beginning.

## Always use `shellcheck` and learn from it

There's not a better resource for learning shell programming than the most important validation tool ever made for shell scripting.

## Tutorials always miss stuff that is in the manual.

Yes, I'm gonna say RTFM. The manual always has more and doing one's own experimentation (instead of watching someone else's) is a much better way to learn.

## Makes extensive use of backticks, a well-known anti-pattern

Everyone who actually knows how to code well in shell uses the safer and nestable `$()` syntax instead of backticks. The nestable syntax even has multiple quote contexts allowing each to contain both double and single quotes just as if they were on the same line. Only an absolute shell noob would recommend using backticks at all. They are only something people should use when doing things from the command line itself as a shortcut, never, ever anything to put into code where they are virtually impossible to read as well. But, then again, if this author even knew about `shellcheck` they would have caught that, but they don't know about it because they are yet another noob producing books without actually learning it first.

## Function section filled with more bad practices than I care to name

Pretty much everything in there is just horrible. Just run any of those examples through `shellcheck` to see for yourself.

## No compare and contrast to bash (the default shell)

When the conversation about "variable scope" happens it doesn't bother to draw the contrast with `ksh` and `bash` (which do have local variable scoping). This could leave readers thinking their only option is globals for everything.

## Use of expr is a well-established anti-pattern

There is no need in 2023 to use `expr` for anything. Research why to find out. Here's what ChatGPT has to say about it:

Using  expr  in shell scripts is considered bad practice for several reasons:

*  Limited functionality:  expr  is limited in terms of the mathematical operations it supports. It can only handle basic arithmetic operations like addition, subtraction, multiplication, and division. Complex mathematical operations and functions are not supported.

* Lack of error handling:  expr  does not provide robust error handling. If any errors occur during evaluation, it often fails silently or produces unexpected results. This makes it difficult to debug and can lead to incorrect script behavior.

* String handling limitations:  expr  is primarily designed for numeric operations and has limited capabilities for string manipulation. It cannot handle advanced string operations, including string concatenation, substring extraction, or regular expression matching.

* Limited portability: Although  expr  is a standard Unix command, its syntax and behavior may vary between different platforms. This can cause compatibility issues when running scripts on different operating systems or shell environments.

Instead of  expr , it is recommended to use more modern and versatile alternatives like the built-in arithmetic expansion  `$((...))` , command substitution, or external tools like  bc  or awk. These alternatives provide better error handling, support complex mathematical and string operations, and offer improved portability across different environments.

## You have to read a web page to do a shell tutorial

This would have been much better as a command that could be executed from a `tmux` window or pane.

## Refers to "CGI scripting" (from 90s)

This proves this content is not only bad, but old.

## No discussion of basic vs extended vs PCRE regular expressions

The assumption is that you just know them, but this is the single biggest source of confusion for beginners.

## Reference to the highly insecure and deprecated `telnet`

Nothing screams "I was written in 1994" more than a reference to `telnet` *at all*.

## Related

* A Guide to POSIX \| Baeldung on Linux  
  <https://www.baeldung.com/linux/posix>
* sh(1p) - Linux manual page  
  <https://www.man7.org/linux/man-pages/man1/sh.1p.html>

