# POSIX Shell Works Everywhere

It's obvious to most that POSIX shell is the choice for coding anything
you want to run everywhere, but what isn't so obvious is that POSIX
shell scripts are even more compatible than Go for stuff. A shell script
can run on ARM or AMD64 with zero changes, not even a stupid
`/usr/bin/env sh` as would be required for `bash`, `perl`, `python`, or
`ruby`. POSIX shell is absolutely king of compatibility. And with `set
-e` set is hands down the most reliable and efficient way to get shit
done fast.

[shell go language]: <https://github.com/rwxrob/zet/search?q=shell%20go%20language>
