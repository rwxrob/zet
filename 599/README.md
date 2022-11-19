# Do Not Depend on `go get` To Install Binaries

It has never been the preferred way to install binaries using `go get`
(as much of a surprise that was to me) and is [deprecated] in 1.17
(which forces the equivalent of `go get -d`:

> Building and installing packages with get is deprecated. In a future release,
the `-d` flag will be enabled by default, and `go get` will be only be used to
adjust dependencies of the current module. To install a package using
dependencies from the current module, use `go install`. To install a package
ignoring the current module, use `go install` with an @version suffix like
`@latest` after each argument. (from version 1.16 go help get)

This is going to cause a full shit-storm of confusion because pretty
much every single package that comes with a binary uses this method in
their INSTALL documentation. Hell, there are tons of books that document
the use of `go get` completely incorrectly based on this. Once again,
there has never been a time to *not* purchase a Go book about anything.
Go version 1.17 is going to seriously break every Go book ever written.

[deprecated]: <https://github.com/golang/go/issues/43684>
