# Command Composer

*Keeping this here for nostalgia since CmdBox is now a thing that
resulted from these original ideas. At the time I had never even heard
of BusyBox.*

Building on the idea from [cmdtab](https://github.com/rwxrob/cmdtab)
where subcommand (actions) are composable and completely independent
from anything else. They simply need to be put into a command directory
and registered with the `main.go` (or main subcommand) in order to work.

What if we created a standard for pulling in these subcommands so that
people can write them in a composable way, and other people can build
commands that composed of these selections of subcommands?

The building is essential to insure security and code validation and
also to allow cross-compilation to target systems on which the main
command (composed of subcommands) will eventually run.

For example, we could use a standard GitHub repo naming convention
(maybe `github.com/<youruser>/cmdtab-<subcmd>`):

```
.git
main.go - simply calls cmdtab.Execute("<subcmd>")
go.mod
go.sum
<subcmd>.go       - standar cmdtab containing <subcmd>
<subcmd>_test.go  - option if needed
```

Perhaps we can even use subcommands and symbolic links to include in the
build. This is no different than how Nginx does configurations after
all.

## Sayings and Couplets

* "Containerization without the container."
* "Remote static linking, static linking from remote sources."

## Requirements

* Everything in one `<subcmd>.go` file for easy inclusion.
