# Go Wall of Shame: Telltale Signs Dev Don't Know Go

This shit drives me so crazy I need to rant about it somewhere. Maybe
someone will actually read it one day and become a better coder. Nothing
says, "I'm a fucking noob" more than the following in your Go code. And
I don't give a *fuck* how "big" the project is. I've seen this shit in
*major* projects. And I'll say it again, the best way to learn good Go
is to find a few *really* good Go projects (start with anything Rob Pike
wrote in the standard library) and dig into them to understand
everything about them.

* Not knowing how to print (yes, I actually found this is a major
   project):

```go
fmt.Printf("\n")
```

* Not combining liked type parameters in a function signature:

```go
func Authenticate(user string, pass string) {
```

* Using `else if`, like, ever:

```go
} else if fileExists(cwd+"/.somefile") {
```

* Using anything at all from the deprecated `ioutils` package. (It has
  been over a year):

```go
ioutils.*
```

* Using anything but `os.UserHomeDir`:

```go
xdgConfigHome := os.Getenv("XDG_CONFIG_HOME")
```

* Using anything but `os.UserConfigDir`

* Using anything but `os.UserCacheDir`

* Using `+"/"+` instead of `filepath.Join`

* Writing lines longer than 100 columns

* Using unnecessarily stupid-long names in small scope:

```go
xdgConfigHome := ...
```

* Using anything longer than three characters for parameter name:

```go
func loadFile(fileName string) {
```

* Printing to stdout instead of logging to stderr:

```go
fmt.Println("No config found")
```

* Initial capitalizing error messages instead of lower case:

```go
fmt.Println("No config found")
```

* Misusing `:=` with `err`

* Using `panic` as a really dumb replacement for throwing exceptions

* Being forced to stay on Go 1.13 'cuz dependencies. Open anything from
   the Kustomize project and read the issues I opened there. It's a
   disaster of a project.

* Squatting on a dozen `golang-` GitHub organizations with nothing but
  bike-shedding markdown confusing the shit out of everyone

    #golang #coding #fails
