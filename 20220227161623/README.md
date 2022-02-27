# So Many Go Modules Smell Like Java

*Caution: strong, justified anger and swears again.*

TL;DR: Don't code Go like Java. Think C or Lisp instead.

When you see a nearly empty `Color` struct with an `Fprintf` method just
to print a fucking color change to the screen you can absolutely smell
the Java stank from a mile away. This personal has fucking idea how
terminal programming works, they just wanted their pretty colors, and so
did everyone else, now it's the dominant package despite how uninformed
its design decisions were. 

Who the fuck wants to call a constructor just to use standard curses
terminal color?! Do you have any idea how fucking stupid it is to force
a method call to change *every* terminal escape sequence every time when
there when a perfectly good constant or variable containing the sequence
would work just fine. 

Oh my god, did you actually force calling *yet another function* just to
combine the escape sequence start with the integer value of the escape?
OMFG, you fucking moron!! That's two *method* calls for ever fucking
attribute change to the screen! You idiot! I mean, are you *trying* to
slow down every terminal application in existence with this shit?

A better approach is to maintain all the supported terminal escapes in
variables that can be emptied to empty strings if a terminal that does
not support them is detected. You know, state management instead of
forcing a function call every fucking time. Oh yeah, you have no idea
what state is, probably 'cuz you coded Java most of your life.

    #rant #java #golang #terminal #curses
