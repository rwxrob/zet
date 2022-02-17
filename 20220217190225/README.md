# Getting Setup for Go 1.18

To get vim support for 1.18 make sure you first install Go 1.18 and then
the `gopls` tool.

```
go install golang.org/dl/go1.18beta2@latest
go1.18beta2 download
go install golang.org/x/tools/gopls@latest
```

Then create a shortcut command (always better than an alias).

```
#!/bin/sh
exec go1.18beta2 "$@"
```

Now you should be able to `:GoUpdateBinaries` from within vim to get
everything to support Go 1.18 development. Until then you will get
annoying syntax errors for using `[ but expected (`.

* Tutorial: Getting started with generics  
  <https://go.dev/doc/tutorial/generics>
* tools/advanced.md at master · golang/tools · GitHub  
  <https://github.com/golang/tools/blob/master/gopls/doc/advanced.md#working-with-generic-code>
* [20210519200444](/20210519200444/) One-Line Shortcut Commands Beat Aliases/Functions
* [20210814162031](/20210814162031/) Burned by Shell Aliases, Again
