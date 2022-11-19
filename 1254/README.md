# Cache or Conf, Where Should I Put My Bonzai Data?

Bonzai was created primarily to replace large, unwieldy collections of
scripts, for individuals and for teams. One thing all of these scripts
inevitably need is a reliable and consistent way to save two main types
of data: configuration data that affects one or more of all those
scripts, and stateful variables that persist between execution.

Configuration data is stored in structured data files all over the
system, or sometimes, in a virtually inaccessible registry. All the
formats are different, even the location for all that config data cannot
be agreed upon despite there being industry standards about it.

Stateful variables are kept in system or environment variables that are
configured in different ways, and are also all over the system. On UNIX
we generally put them into an "rc" file, or, these days, into an `.env`
file. On Windows we add them to the system variables dialog (although
from the command line is doable, it's very annoying).

Bonzai seeks to simplify our terminal-using-and-scripting lives by
centralizing all of this into two distinct files that follow industry
standards for their location and format, YAML (JSON is YAML) for
configuration, and `.key=value` properties for cached variables.

But which one should you use in your `Z.Cmd` commands?

Simply put, `x.C`/`Z.Conf` is for things that are not going to change very
often. That is the reason you cannot change `Z.Conf` values through any
method or function. The only way configuration ever gets changed is
though an interactive editor (unless you break with convention and
code your own non-idiomatic way). `x.Set`/`x.Get`/`Z.Vars` is intended
for all that data that you want to change with code for whatever reason.
And guess what, in a pseudo-IPC-shared-memory sort of way, every command
composed into a single Bonzai tree (my `z` command) can see everything
else. This allows `Z.Cmds` to *very* effectively communicate with each
other without every having to fire off a channel or `Call` them directly
(which you can also do).

How do we reasonably safely share all this cache and configuration in
singular files?

All the `Z.Conf` and `Z.Vars` related `Cmd` methods use the `Cmd.Path`
method to resolve their unique position in the file. So `z tmux set
status coding something` would add the `.tmux.status=coding something`
line to the cached variables file. This simple technique provides a
reasonable amount of net to catch `Cmd` developers during development in
case they make mistakes. Speaking of mistakes ...

How badly your day would be if you blew away the file containing you
data?

This is another good question to ask yourself when deciding where
something should go. Cached variables are meant to be most ephemeral,
delete the file, who cares. Configuration data, on the other hand, is a
big deal. This is where things like your GitHub token should go, that
is, if you want to be sure to update it yourself. If you want your
GitHub token to be ephemeral and reset every time you run something like
`z github login` then that would go into cached variables instead.

Bonzai helps us configure and cache our lives in motion. Happy tree
trimming.

* https://github.com/rwxrob/bonzai

    #golang #coding #bonzai #tips
