# Option to install Cobra commands as command trees instead

By following a simple naming convention and organizing the code appropriately any would-be stand-alone Cobra command can also function as an importable command tree that can be grafted into larger Go Cobra monolith binaries. Here's how. (TODO add reference to `cobracli`.)

Create a Go module. Here's one for a command/tree called `kt`.

```bash
gh repo create
cd kt
go mod init
go work init
go work use .
```

You don't have to create a package at the top. In fact, you probably shouldn't if you have high-level, exported business logic. Put that stuff in another repo.

Create `cmd` as usual plus a subdirectory for the command binary that would normally be at the top of the module..

```bash
mkdir -p cmd/kt
```

Add a `cmd/kt/main.go` file that exports a `Cmd` and calls `Cmd.Execute()` in it's `func main`. 

```go
package main

import (
	"github.com/spf13/cobra"
)

var Cmd = &cobra.Command{
	Use:     `kt`,
	Short:   `Kubernetes tools`,
	Version: `v0.0.1`, // TODO change this to something triggered by tag
}

func main() {
	Cmd.Execute()
}
```

This can be imported by other stuff as `github.com/rwxrob/kt/cmd/kt`.


