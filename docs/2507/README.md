# STOP USING go get -u FOR INSTALLS!

Yet another reason Cobra is fucking brain dead:

> Using Cobra is easy. First, use go get to install the latest version of the library. This command will install the cobra generator executable along with the library and its dependencies:
>
> go get -u github.com/spf13/cobra/cobra

This method of installation has *never* been okay. Use `go install` instead.

