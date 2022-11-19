# Decided to Isolate Exported Go Symbols

Been enjoying a new convention for Go programming that keeps all the
distracting in-line documentation out of most of my code base.

* Put everything public/exported in `<package>.go`
* Stop using `doc.go` and put in `<package>.go` instead
* Put most everything else in `lib.go`
* Don't put *any* documentation in `lib.go` unless necessary
* Favor larger `lib.go` over multiple tiny files
* Break out logic large parts into own files

This way people coming to the code will automatically open the
`<package.go>` file and see the documentation and the public-facing API
and I'll be completely uninhibited by documentation in `lib.go`.

    #golang #coding #conventions
