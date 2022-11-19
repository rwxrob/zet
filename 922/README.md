# Appears `go install` Replaces `go get`

I just accidentally discovered that doing a `go install` against a
command utility Go package downloaded it as well. Perhaps that is why
`go get` is not deprecated for installation and building. That's a much
more sustainable solution even though a log of install docs are going to
have to change.
