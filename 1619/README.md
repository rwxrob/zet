# Bash `while read` from String

Bash has multiple options for this, and they are easy to confuse,
lately I've been using something like `done < <(ls -1)` but `done <<<
$(ls -1)` also works.

