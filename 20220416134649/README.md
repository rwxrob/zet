# Pure Go SQLite3 Module

There's a lot of sqlite stuff out there for Go, but most of it is shit
requiring CGO (which no sane Go dev should do these days without a
really fucking solid reason, you just don't need it). Why throw
cross-compilation out the Window just because some C library has not yet
been ported.

> Package SQLittle provides pure Go, read-only, access to SQLite
> (version 3) database files.
> https://golangexample.com/package-sqlittle-provides-pure-go-read-only-access-to-sqlite-version-3-database-files/

* [20220416134902](/20220416134902/) Importance of CGO_ENABLED=0 for Go Devs

    #golang #sqlite #coding
