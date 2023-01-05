# Go Major Version Path Syncing

I'm just learning about the major version stuff that must coincide with
the tagging. I'm not sure if this has always been there, or if it
sneaked in without my noticing. I went to install `foo` using the following:

```
go install github.com/rwxrob/foo@latest
```

After that failed to do anything:

```
C:\Users\rob>go install github.com/rwxrob/foo@latest
go: github.com/rwxrob/foo@latest: github.com/rwxrob/foo@v1.3.1: parsing go.mod:
        module declares its path as: github.com/rwxrob/cmdbox-foo
                but was required as: github.com/rwxrob/foo

C:\Users\rob>go install github.com/rwxrob/foo@latest
go: github.com/rwxrob/foo@latest: github.com/rwxrob/foo@v1.3.1: parsing go.mod:
        module declares its path as: github.com/rwxrob/cmdbox-foo
                but was required as: github.com/rwxrob/foo
```

It was like my `foo` module had never even been picked up by the caching
servers, because it hadn't. I was totally blown away by this. I was on
version `v2.*`. Why wasn't it finding it? I had no clue, until I tried
(for the hell of it) to get a specific version. Then the error revealed
itself.

```
C:\Users\rob>go install github.com/rwxrob/foo@v2.3.5
go: github.com/rwxrob/foo@v2.3.5: github.com/rwxrob/foo@v2.3.5: invalid version: module contains a go.mod file, so module path must match major version ("github.com/rwxrob/foo/v2")

C:\Users\rob>go install github.com/rwxrob/foo@latest
go: github.com/rwxrob/foo@latest: github.com/rwxrob/foo@v1.3.1: parsing go.mod:
        module declares its path as: github.com/rwxrob/cmdbox-foo
                but was required as: github.com/rwxrob/foo

C:\Users\rob>go install github.com/rwxrob/foo@latest
go: github.com/rwxrob/foo@latest: github.com/rwxrob/foo@v1.3.1: parsing go.mod:
        module declares its path as: github.com/rwxrob/cmdbox-foo
                but was required as: github.com/rwxrob/foo
```

Aha!

```
invalid version:
module contains a go.mod file, so module path must match major version
("github.com/rwxrob/foo/v2")
```

The issue is with `v2` or `v2.*`. As soon as I added a major version
beyond `v1.*` I am *forced* to add a `v2` to the module path in
`go.mod`. That is the first time I have ever heard about this even
though I've see this is the wild for a while and wondered what was going
on. Turns out it's been there since modules were a think, probably 1.13:

> The need for major version suffixes is one of the ways Go modules differs >
from most other dependency management systems. Suffixes are needed to solve the
diamond dependency problem. Before Go modules, gopkg.in allowed package
maintainers to follow what we now refer to as the import compatibility rule.
With gopkg.in, if you depend on a package that imports gopkg.in/yaml.v1 and
another package that imports gopkg.in/yaml.v2, there is no conflict because the
two yaml packages have different import paths — they use a version suffix, as
with Go modules. Since gopkg.in shares the same version suffix methodology as
Go modules, the Go command accepts the .v2 in gopkg.in/yaml.v2 as a valid major
version suffix. This is a special case for compatibility with gopkg.in: modules
hosted at other domains need a slash suffix like /v2.

So TIL v2 is a special thing. Mostly, I learned to never release a major version, like ever. ;)

* Go Modules: v2 and Beyond - The Go Programming Language  
  https://go.dev/blog/v2-go-modules

* https://research.swtch.com/vgo-module

* [20220414164924](/20220414164924/) Having Windows to Test Go Installs is Heaven

    #golang #coding #tips
