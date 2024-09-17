# Install Cobra commands in `pkg/cmd` NOT `cmd`

By following a simple naming convention and organizing the code appropriately according to wider best practices any would-be stand-alone Cobra command can also function as an importable command tree that can be grafted into larger Go Cobra monolith binaries. Here's how. (TODO add reference to `cobracli`.)

Create a Go module. Here's one for a command/tree called `kt`.

```bash
gh repo create
cd kt
go mod init
go work init
go work use .
```

You don't have to create a package at the top. In fact, you probably shouldn't if you have high-level, exported business logic. Put that stuff in another repo that has nothing to do with a command implementation so APIs and other tools can use it.

Create a `pkg/cmd/kt` subdirectory to contain the `cobra.Cmd`. This follows the best practice of keeping importable package code under the `pkg` directory. Thousands of Go projects (including `gh`) already follow this convention (even if `cobra-cli` does not).

```bash
mkdir -p pkg/cmd/kt
```

Add the exported `kt.Cmd` code into `pkg/cmd/kt/kt.go`

```go
package kt

import (
	"github.com/spf13/cobra"
)

var Cmd = &cobra.Command{
	Use:     `kt`,
	Short:   `Kubernetes tools`,
	Version: `v0.0.1`, // TODO change this to something triggered by tag
}
```

This can be imported by other stuff as `go get github.com/rwxrob/kt/pkg/cmd/kt`. But we can make this even better. See that stuttering? Let's get rid of it.

Since the `kt` is the top-level command under which all the other sub commands and sub command trees go, we can pull that specific `kt.Cmd` up one level into `pkg/kt/cmd/kt.go` to avoid stuttering in the import lines which become the very elegant `go get github.com/rwxrob/kt/pkg/cmd` and `import kt "github.com/rwxrob/kt/pkg/cmd"`. The rest can keep their own subdirectories into which even more subcommands can be added and everything just makes sense.

You might also have to `go get github.com/spf13/cobra` to get it.

Now create the `cmd` for the main command but unlike Cobra, created a subdirectory for the command *binary* that would normally be at the top of a Cobra repo/module. Again, we are following the well-established best practices for the entire Go community which have generally said that *nothing* should ever go into `cmd` that doesn't have a `main` package. This is for entry-point *commands*!

```bash
mkdir -p cmd/kt
```

Add a `cmd/kt/main.go`

```go
package main

import kt "github.com/rwxrob/kt/pkg/cmd"

func main() {
  kt.Cmd.Execute()
}
```

The beauty of this is that any developer doing that import immediately disambiguates `pkg/cmd` from `cmd` in the way that all Go developers have been trained to, command binaries in `cmd` and importable packages in `pkg`.

Now to create a binary from any exported command under `pkg/cmd` all that is needed is to add a wrapper under `cmd` for that specific command, which can also be organized with the same structure as the command tree itself. Every single command could have it's own individual binary if you wanted, or the root command can be the only thing released but the docs on the `pkg/cmd` will show developers that they can create their own combinations of these exported commands.
