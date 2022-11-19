# Personal Go Project Testing Conventions

I have a particular preference from among the many Go testing
conventions. My goals are simplicity (for user/reader) and
sustainability above all.

**Put all examples in `examples_test.go`** and no I don't care how many
there are, they all go in there so people can grep through it and see
everything they need without using a web browser. This means I use the
`package foo_test` first line to force.

**Include `example_test.go` if problematic** because a lot of libraries
and command modules don't do well with package importing at all. This is
in addition or instead of `examples_test.go`.

**Only use local scope in `foo_test.go`** where having to import the
package just slows down the creation of tests that really are not
intended for any user to read at all. These use `package foo` as the
first line.

**Prefer examples over local tests** because they are not only more
intuitive to write but also for *anyone* to read. Sure you have to make
your tests fit within something that can be evaluated by an
`fmt.Println` but who cares, it makes the entire collection of tests
much more digestible and sustainable. I fucking hate obfuscated tests.

**Prefer fuzz tests when needed** because their are some cases when
localized, completely unintelligible fuzz tests make sense to make sure
you are actually not allowing something through that shouldn't be. Use
names like `foo_fuzz_test.go` to warn people just by looking at it.

**Just use the standard test package** instead of whatever the flavor of
test library of the week turns out to be. No need to force maintainers
to have a dozen different test packages to learn. Stick with the
standards. They are perfectly fine for almost every project. Who cares
if you have to write a bit more code. You drop a dependency and make
your maintainers lives that much simpler later. Test code is read much
more than written, take more time to write the tests using the standards
so that everyone reading them later understands them. Honestly, you just
don't need it. Why on Earth would you discard one of Go's greatest
advantages: a consistent test framework.

    #golang #testing #conventions
