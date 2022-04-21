# Stop Using Single Brackets in bash!

There's a very good reason that bash designers added double bracket
conditions. Because POSIX single brackets are a fucking disaster. Do you
use `-eq` or `=`? Do you have to quote things? How about strings? What
the fuck is up with glob expansion?

Seriously, if you are using single brackets in 2022 in *anything* where
you have permission to use bash you are a fucking moron (or just
uninformed). I'm not even going to tell you all the reasons this is
simply an objective fact. If you don't know why, I challenge you to do
the research and read everything you can (starting with `man bash`) as
to why that is.

POSIX shell scripts are horrible, broken, boomer standard that most of
its creators don't even use anymore. 99% of the time you can use bash
without a problem. Zsh scripts are even worse because they *look* like
POSIX scripts but have company-killing floating point math problems in
them waiting to burn you without you even knowing it. Zsh is NOT POSIX
compliant. It's fucking dangerous. If you deploy a zsh script in
production you are a FUCKING MORON!

I'm so fucking tired of defending this position. It's so annoying.

By the way, if you are doing any numeric comparisons and math you should
be using double parentheses instead.

And you are using `shellcheck` right? What?! You've never heard of it?
Okay, we're done here.

    #bash #posix #rant #shell #scripting
