# Don't Let Floor Division Ruin Your Day

Floor division is the *default* for C, Python 2, POSIX Shell (NOT Zsh),
bash, and Go. But there's a good chance what happens with you divide three by two isn't what you expect, at first. Would expect 3/2 = 1? Probably not, but that is exactly what floor division is. To get around this, always add a decimal point to your number when you care about such things (3.0/2=1.5). There's not much more do say about this except to make sure the language you are using does what you expect.

Another safety measure is to never do direct equality when checking conditions involving numbers. Use greater than or less than since they will always work, even if you make a mistake like the one involving floor division, to a point.
