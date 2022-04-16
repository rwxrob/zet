# Pure Go SQLite3 Module

There's a lot of sqlite stuff out there for Go, but most of it is shit
requiring CGO (which no sane Go dev should do these days without a
really fucking solid reason, you just don't need it). Why throw
cross-compilation out the Window just because some C library has not yet
been ported.

SQLittle looks promising, but misses on so many levels. It is definitely
something that could be built into something worth using, but it isn't
at that level at the moment. After all, it's just a "for fun" project.

> Package SQLittle provides pure Go, read-only, access to SQLite
> (version 3) database files.
> https://golangexample.com/package-sqlittle-provides-pure-go-read-only-access-to-sqlite-version-3-database-files/

* Top 23 Go Sqlite Projects (Apr 2022)  
  https://www.libhunt.com/l/go/topic/sqlite

* [20220416134902](/20220416134902/) Importance of CGO_ENABLED=0 for Go Devs

    #golang #sqlite #coding
