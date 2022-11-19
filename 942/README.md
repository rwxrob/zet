# Bash Completion `COMP_LINE` Only Current Command

When a command is receiving standard input from a pipe on the Bash
command line the entire line is not set for `COMP_LINE`, only everything
from the bar on. This makes sense since each pipe is a separate subshell
now that I think about it. But I was concerned that the `COMP_LINE`
might have been more complicated and I missed it. Bash completion with
`complete -C foo foo` is just brilliant. I'm blown away that more people
don't use it.
