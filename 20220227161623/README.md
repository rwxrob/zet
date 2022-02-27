# So Many Go Modules Smell Like Java

TL;DR: Don't code Go like Java. Think C or Lisp instead.

Been updating the `term/esc` stuff just casually glancing through
several other popular Go modules and honestly, most of them are absolute
shit. The most recent one (which I won't name) unnecessarily throws out
the entire efficiencies and best-practices of decades of terminal
attribute and color management just to make it use structures with
methods instead. It's like the person creating it still had a diseased
Java brain when they did. I mean, who the fuck wants to call a
constructor just to use standard curses terminal color, let alone call a
fucking function to write a terminal escape sequence every time when
there when a perfectly good constant or variable containing the sequence
would work just fine. That's evidence that the person coding it has
absolutely no fucking idea how terminal programming works, they just
wanted their pretty colors, and so did everyone else, now it's the
dominant package despite how fucking uninformed its design decisions
were.

A better approach is to maintain all the supported terminal escapes in
variables that can be emptied to empty strings if a terminal that does
not support them is detected. You know, terminal state management
instead of forcing a function call every fucking time.
