# Go SemVer Package Options

* golang.org/x/mod/semver
* github.com/rogpeppe/go-internal/semver

There are a ton of alternatives, but both of these are semi-supported by
the Go team. I'm usually going to use go-internal because I already am
married to it for `lockedfile` (which is the *only* way to do safe,
system-wide file writes and has been proposed for inclusion in the
standard library). The maintainer `rogpeppe` has also authored some
interesting Go books.

    #golang #coding #tips #semver
