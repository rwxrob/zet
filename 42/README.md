# Perl Has No Place in Container OS Distros

I was recently complaining about `sed` but remembered that `perl`,
although it does regex way better than `sed`, has no place in the small
BusyBox and Alpine and other container distributions. It's way too much
bloat to justify it. BusyBox, includes `sed` and `cut` and `tr` and even
`awk` so they are the standard for POSIX shell scripts and probably
should be.

Related:

* [20210502005834](/20210502005834/) Problems with `sed`
