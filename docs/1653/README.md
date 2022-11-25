# YOU Are the PHONY if You Abuse Makefiles

I am so *fucking* tired of opening intensely complicated and just
fucking stupid Makefiles that could have easily been written as a simple
shell script with functions. Guess what, "production" Kubernetes
software is fucking full of them. I have one questions for the morons
who write these things:

WWWWHHHHHHHYYYY?

If you have a dozen `.PHONY` rules and not a single fucking dependency
rule in your entire 100 line Makefile you are a fucking jack ass. You
have just forced everyone coming after you to maintain that shit. Why?
To flex about your make skills? Because some stupid boomer, greybeard
told you that was "the right way" to do it? Well it's not, making tech
unnecessarily complicated and inefficient is never the "right" way.

"How inefficient?"

Because every fucking line in a Makefile rule invokes a *separate*
subshell for no fucking reason.

Seriously, I really want to slap someone right now. Please, please, I
bet you, don't read for `make` until (and if) you ever need it. You will
save someone the pain and suffering of wanting to find and do violent
things to you.

    #rant
