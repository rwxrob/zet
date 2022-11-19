# Working Out the GitHub API Common Commands Branch

At a cross roads, I need `z update` to automatically the currently
running process binary from the latest GitHub release matching the
`Source` for the given `GOOS` and `GOARCH`. Up to now I've been writing
my own GitHub API queries (which work fine enough) but it's really hard
when the `gh release` command does everything I need to do. If I use
`gh` then I force a dependency to download the `gh` tool (or get it
somehow). If not, I have to rewrite the API code that `gh` already
contains (and it is too spaghetti to pull out of it, which is really too
bad).

I could embed a specific version of the `gh` binary. In fact, that might
a part of the embedded assets thing. There's nothing that says an
executable couldn't go along for the ride. I can think of a lot of
reasons to want to have the latest `gh` binary tightly coupled with my
`z` tool (and other tools I'm writing for work). Having the `gh` tool
would be so valuable for so many reasons (outside of the immediate need
to do logins).

After playing with `gh release view --json` I realize there is really no
reason not to encapsulate `gh` with anything I need and just expect the
`gh` tool to be installed. After all, it's also a Go monolith that can
be installed anywhere and updates itself. It's really the standard
everyone should learn instead of creating yet another tool that talks to
the GitHub API directly.

So really, all I have to do is translate the `getopt` shit into Bonzai
bliss. Then I can create some high-level function `pkg` calls that
encapsulate the `gh` calls. Sure there's a level of indirection that
could be avoided. But I just don't see how going against the `gh`
official tool will ever end well. To lessen the blow I can have `z
install gh` and `z setup gh` in ways that play nice with `vars` and
`conf`.

    z gh repo rwxrob/bonzai            - raw json
    z gh rel rwxrob/bonzai@latest      - json for specific release
    z gh latest rxrob/bonzai           - name/semver of latest release
    z gh dl tar rwxrob/bonzai@latest
    z gh dl file rwxrob/bonzai@latest <name|regex>

I realize that these commands look a lot like the `go install` stuff but
they are meant to work on systems where there is no Go installed. The
familiarity is by design.

I want the `dl|download` command to be smart about detecting the `GOOS`
and `GOARCH` and guessing well about which one is wanted when not all
the `name` is there. By default, if the name doesn't match anything it
should find the closest one based on something like this:

1. `<name>`
1. `<name>_GOOS_GOARCH`
1. `<name>_GOOS`

And if the name isn't a name (starts with a slash `/`) then should
assume a regular expression.

Whether or not there is a prompt to continue with the download is a
`z gh dl conf` setting, probably `prompt=false`. By default the prompt
will be off if not `term.IsInteractive`, otherwise will be sure want to
download the file given the magic matching going on. Could be a lot of
stuff there.

