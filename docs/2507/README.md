# STOP USING go get -u FOR INSTALLS!

Yet another reason Cobra is fucking brain dead:

> Using Cobra is easy. First, use go get to install the latest version of the library. This command will install the cobra generator executable along with the library and its dependencies:
>
> go get -u github.com/spf13/cobra/cobra

This method of installation has *never* been okay. Use `go install` instead. Thankfully, this is now actively blocked:

```
$ go get -u github.com/spf13/cobra/cobra
go: go.mod file not found in current directory or any parent directory.
        'go get' is no longer supported outside a module.
        To build and install a command, use 'go install' with a version,
        like 'go install example.com/cmd@latest'
        For more information, see https://golang.org/doc/go-get-install-deprecation
        or run 'go help get' or 'go help install'.
```

I expected as much from a project that actively encourages printing all error messages to standard output (instead of standard error) and has no fucking clue why that's a horrible idea.
