# Torn Between Monolith Config or Factored

This whole `z` Bonzai tree thing has me really thinking about the best
personal/private configuration setup. Part of me really likes the idea
of having it all in a central `~/.config/z/config.yaml` file. But I also
like that you can add `config` to any other command and have it apply to
just that one. But when that happens it assumes the name of that
command goes in `~/.config/` which could have conflicts with other
identically named Bonzai branches even though they are under other
branches. For example, `bot` I had under Twitch and wanted to add
`config` to it and realized that if I had another `bot` under `irc` or
something that the `~/.config/bot` config files would conflict. This is
why the applications in Windows have such unique names and those long
fucking directory names, to avoid this conflict. At least I have
everything organized into a tree already under `z`. The question is how
to alter the `config` command to intelligently know where it is in the
chain, and where to put those files, or to keep everything in a single
file. A single file still seems like the best, one file to rule them all
that you can backup to private git repo. If what I want to save would
bloat the file then it belongs someplace else and can add a config entry
to point to that location, like the `bot` `commands.yaml` file.

I could make the `config` command automatically point to the root for
the application (binary) itself. It forces edits directly with editor so
that would be consistent. The tough part would be how does something
like the `bot` command know what configuration parameter to look up? I
suppose any Bonzai branch knows it place in the tree and could infer the
lookup.

