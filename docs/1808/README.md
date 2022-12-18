# Golang SQLite3 options, CGO?

To CGO or not to CGO, that is the question. "It depends" is always the answer. If we do, we get some kick-ass speed and official compatibility with the `database/sql` standard Go interface. We also are immediately ready to write a compatible API in C directly. But, building for CGO is a *pain in the ass*.

The problem is that you really pay for performance when you drop the C library:

>    This post summarizes some basic ingestion and query benchmarks using mattn/go-sqlite3 and modernc.org/sqlite. tldr; the Go translation is between twice as slow and 10% slower for both small datasets and large, for INSERTs and SELECTs.

Another advantage of just accepting our CGO fate is that later I can incorporate other C things (more notable for Python stubbing than anything) and be ready for it.

Still, adding a CGO dependency to *this single thing* will force every fucking Bonzai monolith that includes a command branch that uses this to use CGO even if it is just for that single branch. There is *no way* that is worth it. So the answer is NO CGO --- ever. I don't care how much a perf hit we take. The load is already distributed across different instances of keg directories. And, if it every came to it, we can replace the internal non-CGO API with one that is, no premature optimization.

* GitHub - glebarez/go-sqlite: pure-Go SQLite driver for Go (SQLite embedded)  
  <https://github.com/glebarez/go-sqlite>
* sqlite package - modernc.org/sqlite - Go Packages  
  <https://pkg.go.dev/modernc.org/sqlite>
* GitHub - mattn/go-sqlite3: sqlite3 driver for go using database/sql  
  <https://github.com/mattn/go-sqlite3>
* Golang SQLite database/sql - Earthly Blog  
  <https://earthly.dev/blog/golang-sqlite/>
* Golang SQLite3 Tutorial \[With Examples\] \| GoLinuxCloud  
  <https://www.golinuxcloud.com/golang-sqlite3/>
* Go and SQLite in the Cloud  
  <https://www.golang.dk/articles/go-and-sqlite-in-the-cloud>
* Go sqlite3 - working with sqlite3 in Golang  
  <https://zetcode.com/golang/sqlite3/>
* SQLite in Go, with and without cgo  
  <https://datastation.multiprocess.io/blog/2022-05-12-sqlite-in-go-with-and-without-cgo.html>
* cznic / sqlite · GitLab  
  <https://gitlab.com/cznic/sqlite>

By the way, looked at `cvilsmeier/sqinn-go` which is so bad it's comical. Strong recommendation to stay the hell away from it, but you'll get that sense immediately when you read "listed in some-dumb-ass's" awesome-go list."
