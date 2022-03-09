# Go Wall of Shame: Telltale Signs Dev Don't Know Go

This shit drives me so crazy I need to rant about it somewhere. Maybe
someone will actually read it one day and become a better coder. Nothing
says, "I'm a fucking noob" more than the following in your Go code. And
I don't give a *fuck* how "big" the project is. I've seen this shit in
*major* projects. And I'll say it again, the best way to learn good Go
is to find a few *really* good Go projects (start with anything Rob Pike
wrote in the standard library) and dig into them to understand
everything about them.

1. Not knowing how to print (yes, I actually found this is a major
   project):

```go
fmt.Printf("\n")
```

1. Using `else if`, like, ever:

```go
} else if fileExists(cwd+"/.somefile") {
```

1. Using anything from deprecated `ioutils`:

```go
ioutils.*
```

1. Using anything but `os.UserHomeDir`:

```go
xdgConfigHome := os.Getenv("XDG_CONFIG_HOME")
```

1. Using anything but `os.UserConfigDir`

1. Using anything but `os.UserCacheDir`

1. Using `+"/"+` instead of `filepath.Join`

1. Writing lines longer than 100 columns

1. Using unnecessarily stupid-long names in small scope:

```go
xdgConfigHome := ...
```

1. Using anything longer than three characters for parameter name:

```go
func loadFile(fileName string) {
```

1. Printing to stdout instead of logging to stderr:

```go
fmt.Println("No config found")
```

1. Initial capitalizing error messages instead of lower case:

```go
fmt.Println("No config found")
```

1. Misusing `:=` with `err`

1. Using `panic` as a really dumb replacement for throwing exceptions

1. Being forced to stay on Go 1.13 'cuz dependencies. Open anything from
   the Kustomize project and read the issues I opened there. It's a
   disaster of a project.

    #golang #coding #fails
