# Rethinking Standard Bonzai Repo Structure

I know `pkg` is common, but it's grating on me. People generally expect
the high-level functions of the API to be at the top-level of a repo.
And I think I need to go back to the `cmd` directory since that is so
well established and there might be some repos that have multiple
standalone commands. The proposed changes would look like this for a command
called `foo`:

```
.git
.gitignore
.github
README.md
CONTRIBUTING
cmd/foo/main.go (package main)
foo.go (traditional library package foo)
foo_test.go
cmd.go (home of foo.Cmd)
go.mod
go.sum
go.work.off
```

I *really* want to keep the trend going of having high-level functions,
with a standalone command, and a composable Bonzai branch all in the
same repo so people can consume the code in different ways.

This change is really going to hurt since I have so much stuff pointing
to things assuming Bonzai branches are the main thing. But the Go
community will not expect that. They will, however, be curious to see
what this "z" directory is all about. The rest would be very intuitive.

Everything in this repo will have the same version/tag as well.

I'm going to make this change to everything tomorrow during my last day
of vacation. I think I'll put together some more notes that can go in
the Bonzai book, which I want to have at least started by the beginning
of the Beginner Boost. It just makes building useful things in Go so
much easier and faster.

    #golang #bonzai #design
