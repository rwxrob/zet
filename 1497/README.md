# Prefer `kubectl --overrides` to `--annotations`

The syntax of the command line option `--annotations` is tough to
remember and generally redundant and unnecessary if you learn to use
`--overrides` even though it's a lot more to type out. I prefer
`--overrides` because it very explicitly spells out the exact JSON used
from the would be fields file. This reinforces my understanding of the
syntax of the files and works universally whenever doing anything from
the command line. But usually this sort of stuff pushes the need for
a separate file.

