# Bonzai command branch go module structure

No Go project should ever have a `main` package at the top of the repo. Early in Go's life some people did that for incredible simple commands, but those days are long gone. Any `main` package should always be someplace under the `cmd` top level directory. This leaves every place else free to define exportable business logic and composable commands.

Bonzai branches are contained in Git repos that have both top-level
functions and structures as well as the reserved `Cmd` base struct and
other exported command structs with the `FooCmd` convention. The `cmd`
directory always contains another directory (usually the same name as the repo
itself) containing a light wrapper in a `main.go` file that executes the `Cmd`.

The advantage of this combination is that both high-level functions can
be combined with actual commands that use those high-level functions.
This is an optimal combination when creating composable code libraries
and command line tools.

* https://github.com/rwxrob/bonzai-example

```
go install github.com/rwxrob/z@latest
```
