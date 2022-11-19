# UNIX/Linux Subshell Versus Subprocess

*Thanks for Frans Nylund for this clarification.*

A subshell gets created when the shell ONLY performs a `fork()` system
call. It will hence be (almost) an exact copy of the parent, which means
it will inherit the process id, aliases, functions, local variables,
etc. It does NOT exec. No need to export anything. Any changes made to
the subshell does NOT affect the parent shell. The output of the
subshell is visible in the parent shell because the subshell inherits
the file descriptors from the parent.

A subprocess gets created when the shell performs BOTH a `fork()` AND an
`exec()` system call. Because the exec overlays the memory and all that,
it means all the aliases, functions and local variables are lost. This
is why we need to export variables, functions, etc. Any changes made to
the subprocess does NOT affect the parent shell. The output of the
subprocess is visible in the parent shell because the subprocess
inherits the file descriptors from the parent.

For example, running a script creates a subprocess (NOT a subshell).
Meaning it does `fork()` AND `exec()`, just like what would have happened if
we executed any other program (`ls`, `cat`, `echo`, etc). Subshells CAN be used
inside (and outside) scripts by doing stuff like:

```bash
(cmd)

cmd | cmd

$(cmd)

cmd &
```

etc... but the script ITSELF is a subprocess.

Sources(check Gilles' answers).

Related:

* <https://unix.stackexchange.com/questions/138463/do-parentheses-really-put-the-command-in-a-subshell>
* <https://unix.stackexchange.com/questions/261638/is-a-sub-shell-the-same-thing-as-a-child-shell>
* <https://unix.stackexchange.com/questions/442692/is-a-subshell>
* <https://mywiki.wooledge.org/SubShell>
