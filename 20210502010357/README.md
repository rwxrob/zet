# Perl Has No Place in Container OS Distros

I was [recently](20210502005834) complaining about `sed` but remembered
that `perl`, although it does regex way better than `sed`, has no place
in the small BusyBox and Alpine and other container distributions. It's
way too much bloat to justify it. BusyBox, includes `sed` and `cut` and
`tr` so they are the standard for POSIX shell scripts.
