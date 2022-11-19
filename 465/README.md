# BusyBox and Alpine Mean POSIX Shell Dockerfiles

The container world is dominated by ultra-light containers that are
built almost uniquely on BusyBox and Alpine (if not around single
executables such as Go stuff built with CmdBox). Alpine had its own
first conference in 2021 due to increased popularity from cloud-native
usage.

These realities practical mandate the use of POSIX shell in *all*
Dockerfiles as an industry best practice. While it is true that you can
write Dockerfiles using whatever the shell supported on the base
container  (such as `bash` on Ubuntu) why would would any reasonable
person inflict that level of confusion on themselves (and their support
teams). Just use POSIX. Everyone stays happy. For Dockerfiles POSIX is
more than enough and performance is not an issue for the few times a
Dockerfile must be executed.

For rapid prototyping obviously a heftier scripting language such as
Perl, Python, even Node are preferred. But Bash is probably a bad pick,
because it will inevitably infect your POSIX shell code and your mastery
of POSIX shell itself. To keep safe, always use `shellcheck` for that
stuff.
