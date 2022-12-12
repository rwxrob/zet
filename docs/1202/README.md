# Use `lockedfile` to properly lock file in Go

***Update Monday, December 12, 2022, 7:56:22AM EST:*** Windows WSL2 shits the bed when trying to use the standard `go-internal` `lockedfile` command returning a `Lock keg: Incorrect function.` error that looks like is because WSL2 is *not* Linux, at all. I will *never* be fooled into using WSL2 for anything ever again. VMware has never failed me.

```
rwxrob@tv:~/blah$ /mnt/c/Users/rob/Downloads/keg-windows-amd64.exe init
Lock keg: Incorrect function.
```

***Update:*** Kubernetes has fixed one of the places where they were doing this wrong. (https://github.com/kubernetes/kubernetes/pull/107354). Always feels good to have someone respond to an issue you take the time to create. Thank you!

After hours of reading and research I've found the best way to open files locked for safe writing and reading. The `lockedfile` package is used internally by the Go project and is *very* robust. It even has fixes for edge cases on AIX. It's no surprise that there has been a proposal to make it public and that there is a supported repo with all the `go-internal` stuff as well. Seriously, if you are opening files for safe writes you should really be using this (and only this). Tons of big projects don't have a fucking clue how to do this correctly and are just blatantly wrong (including Kubernetes in several different places). Now you know how to do it right.

I've put my copy of the `go-internal` `lockedfile` package into my own `fs` package for convenience, but using it from the other location is fine as well. The important thing is to use the `lockedfile` package as-is because you have the greatest possibility of creating code that is 100% compatible with the proposed new standard for doing this.

* <https://github.com/rogpeppe/go-internal>
* <https://github.com/golang/go/issues/33974>

