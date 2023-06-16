# Use Go `internal` to not export symbols

> Go's package system makes it easy to structure programs into components with clean boundaries, but there are only two forms of access: local (unexported) and global (exported). Sometimes one wishes to have components that are not exported, for instance to avoid acquiring clients of interfaces to code that is part of a public repository but not intended for use outside the program to which it belongs.
>
> The Go language does not have the power to enforce this distinction, but as of Go 1.4 the go command introduces a mechanism to define "internal" packages that may not be imported by packages outside the source subtree in which they reside.
>
> To create such a package, place it in a directory named internal or in a subdirectory of a directory named internal. When the go command sees an import of a package with internal in its path, it verifies that the package doing the import is within the tree rooted at the parent of the internal directory. For example, a package .../a/b/c/internal/d/e/f can be imported only by code in the directory tree rooted at .../a/b/c. It cannot be imported by code in .../a/b/g or in any other repository.
>
> For Go 1.4, the internal package mechanism is enforced for the main Go repository; from 1.5 and onward it will be enforced for any repository.


I suppose I've never worked on a big enough project to care about the implications of too much public API exposure, but I certainly appreciate the concerns of large projects to protect themselves from such tight coupling that could ensue. Well, I was today-years-old when I learned about `internal`. I was, like, "What the fuck is up with all the `internal` subdirectories in this Kind dependency path? Now I know why.

The `internal` directory is specifically known to the `go` compiler (like `testdata`) and nothing in it can be used by anything that doesn't "share an ancestor" meaning, that things are "internal". You can always start with it and put everything in there and then just promote it later if you need.

Perhaps the biggest advantage is that you can name stuff as you would anywhere else, even avoid the problem with tagged JSON/YAML by leaving things "public" but in the `internal` directory.

* Use internal packages to reduce your public API surface \| Dave Cheney  
  <https://dave.cheney.net/2019/10/06/use-internal-packages-to-reduce-your-public-api-surface>
* Official internal package documentation  
  <https://golang.org/doc/go1.4#internalpackages>
