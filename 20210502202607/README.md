# Bash Internals are Bloated Mess, Including TCP

Was talking with someone in the community about Bash internals having
reviewed the inner source Code. "Did you know Bash has a full TCP/IP
stack built in?" I knew there was a lot there. And I've always known
that the reason the Zsh and Dash/Debian people dislike Bash is because
of how fucking bloated it has become, without reason. But it wasn't
until talking with him that realized how badly my beloved Bash actually
is inside. Bash will *never* be more than a great default interactive
login shell. If I never code another line of it in a script I'll be
fine. I can't get behind that shit. POSIX or die (wait that's Perl,
hardy-har).
