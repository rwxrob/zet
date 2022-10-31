# Go Internal Requires Local Tests

Moving something to anything under an `internal` directory in Go
automatically forces use of localized tests --- even when using example
tests.

This is something of a discovery, because one of the advantages of using
internal with exported symbol names is that you don't have to mess with
a lot of code, you can just cut and paste it into the new location under
`internal` someplace. But, such is not the case if you are moving
example-based tests that use the `package *_test` method.

Obviously, this makes sense, because the whole point of `package *_test`
is to produce examples that read as they would be used by a user of the
package, but since they are under `internal` no user will ever be able
to use that package (except other code within the same module).

I've decided to start limiting my example based tests to
`example_test.go` and use localized tests (including example based just
for the simplicity) in everything else since localized test code is more
portable during refactoring and reorganization.
