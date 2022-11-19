# Using `replace` in `go.mod` Will Blow Up Your Module

> 🤬
> More evidence the Go modules projects is the biggest clusterfuck in all of Go history.

It appears as of Go 1.16+ use of the `replace` directive for clever
things like rerouting a different domain name or realistic things like pseudo-aliases for location will blow up your module when people use the *new* standard way to install modules directly from the Internet. Here's an example of the rather significant `kubernetes/kompose` project blowing up from this:

```
$ go install github.com/kubernetes/kompose@latest
go install: github.com/kubernetes/kompose@latest (in github.com/kubernetes/kompose@v1.26.1):
	The go.mod file for the module providing named packages contains one
  or more replace directives. It must not contain directives that 
  would cause it to be interpreted differently than if it were the 
  main module.
```

This looks like the result of moving from `go get` to `go install` since
this is explicitly called out in the proposal.

> If that module has a  go.mod  file, it must not contain directives
> that would cause it to be interpreted differently if the module were
> the main module. In particular, it must not contain  replace  or
> excluded directives.

Related:

* Go Modules Reference - The Go Programming Language  
  <https://go.dev/ref/mod>
* Why is GO111MODULE everywhere, and everything about Go Modules (updated with Go 1.17) \| maelvls dev blog  
  <https://maelvls.dev/go111module-everywhere/>
* <https://github.com/golang/go/issues/40276>
* <https://github.com/golang/go/issues/30515>
* <https://golang.org/issue/26640>

Tags:

    #golang #fails #modules #gotchas
