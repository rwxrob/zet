# "Should I use suffixes on my shell scripts?"

TL;DR: No. It violates UNIX philosophy.

1. A shell script with a suffix cannot be replaced with a compiled
   program or a rewrite in a more substantial scripting language later.

1. The shebang line covers all syntax matching editor issues.

1. Only Windows really cares about suffixes

If the file isn't a script, but something that is sourced from another script, then adding a suffix does make a lot of sense.
