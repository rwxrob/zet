# Importance of CGO_ENABLED=0 for Go Devs

Every Go programmer, novice or veteran, should have the following in
their system environment variables:

```sh
export CGO_ENABLED=0
```

This will keep you from doing stupid shit like using a package --- or
even a standard library function --- that requires C to compile. You
just do not need to do this in 2022. There are so many pure Go
alternatives that the thing you think you need has a better, more
modern, pure Go version you just don't know about (just look at SQLite
support, for example).

    #golang #coding #tips
