# Don't Code for Millions of Colors in Terminal

*Terminal color is juvenile. (Rob Pike)*

While I do not agree with Rob Pike at all on this one. Everyone is
tempted by the new support for modern terminals with millions of colors,
but there are some very modern reasons not to ever use them.

The standard eight terminal colors are used by *all* terminal theme
software. This means that when you specify a precise color instead of
using one of the standard you are deliberately forcing the user to use
your color instead of what they picked for their current theme. It is
the equivalent of how the Web failed miserably when CSS came to be
because the user lost all control of how they consumed the content. The
polite/right thing to do is allow the user to set their theme as they
like, and the simpler, more limited color palette completely supports
that.

So please, unless you are taking over the entire terminal and
controlling every fucking curses cell, use the standard, user-controlled
basic ANSI color escapes and nothing more. Everyone will be glad you
did.

    #rant #colors #terminal
