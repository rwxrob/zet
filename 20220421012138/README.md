# Bonzai Command Branch Go Module Structure

Bonzai branches are contained in Git repos that have both top-level
functions and structures as well as the reserved `Cmd` base command and
other exported commands with the `FooCmd` convention. The `cmd`
directory contains another directory (usually the same name as the repo
itself) containing a light wrapper in a `main.go` file.

The advantage of this combination is that both high-level functions can
be combined with actual commands that use those high-level functions.
This is an optimal combination when creating composable code libraries
and command line tools.

* https://github.com/rwxrob/bonzai-example

```
go install github.com/rwxrob/z@latest
```

Why would I complicate that?

    #golang #bonzai #coding #tips
