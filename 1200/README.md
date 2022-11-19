# Using `go get -u` is Usually Bad, Beware

Beginners to Go might see be doing `go get -u` with wild abandon and
think they should also. But the reality is that `go get -u` should
almost never be used --- especially now that we have `go work`.

The reason is because this command updates *everything* without
consideration for what should be updated. Every dependency with every
version is automatically updated to the latest without any opportunity
for you to vet the differences between the versions. Updating your
versions, or using anything like the dumb-shit NPM "or greater than"
option is a recipe for disaster on multiple levels.

I know you don't want to be reminded of it, but you should know *every
fucking line of code that exists in your applications*. That means you
must really trust the package team or have a team of your own vetting
all the code that you import. Using `go get -u` is the antithesis of
this because it does everything at once.

Instead, you should probably create a regular process of reading through
your core dependencies in `go.mod` (which are nicely organized for you
to review, unlike Node shit). You then `go get -u foo` on each
individual one instead of all of them.

    #golang #coding #tips
