# I prefer internal over private scope in Golang

Use of the `internal` package evolved much later in the lifetime of the Go programming language. Everything in it is only available to the package containing it from that level and below. Placing an `internal` at the top level of a module has become one of my favorite ways to organize code well. Sometimes I am not sure if I want something exported or not (and all the hassle of supporting backward compatibility for everything that could become dependent on it) yet there is a chance I might. In such cases `internal` is perfect because I can write and document whatever it is just as if it were being exported, capitalization and all. Then if I do decide to export it, I can just move the files into the exported package space someplace (outside of `internal` package).

I only use private scope for really localized things.
