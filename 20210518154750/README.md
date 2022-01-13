# `go get` is Now `go install` or `go get -d`

Just ran across this in the Go documentation for `get` that really is
going to make a lot of Install sections of `README.md` files all over
just plain wrong. To be clear, `go get` will no longer be able to be
used to install Go commands (and even packages). This is fucking huge.
That is a *major* change of expectations from the entire community.

> The -d flag instructs get not to build or install packages. get will
  only update go.mod and download source code needed to build packages.
>
> Building and installing packages with get is deprecated. In a future
  release, the -d flag will be enabled by default, and 'go get' will be
  only be used to adjust dependencies of the current module. To install
  a package using dependencies from the current module, use 'go
  install'. To install a package ignoring the current module, use 'go
  install' with an @version suffix like "@latest" after each argument.

Related:

* Deprecation of \'go get\' for installing executables - The Go Programming Language  
  <https://go.dev/doc/go-get-install-deprecation>
* go get: installing executables with 'go get' in module mode is deprecated. \| by Ravindra \| Medium  
  <https://medium.com/@sherlock297/go-get-installing-executables-with-go-get-in-module-mode-is-deprecated-de3a30439596>
* Deprecation of \'go get\' for installing executables - The Go Programming Language  
  <https://docs.studygolang.com/doc/go-get-install-deprecation>
