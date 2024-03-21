# Go Gin still better than new 1.22 net/http

I was reminded by my coworker that Gin has much better handling of chaining and conditional branching through connected middleware. The new net/http might have a lot of great stuff, but it still lacks that very fundamental requirement of any good web framework. Any substantial API will demand the middleware handling Gin provides. Gin continues to be several levels above every other offering as well:

* The most mature and stable
* Most documentation of any framework
* Greatest enterprise adoption
* Huge library of pre-made middlewares to incorporate
* Simplest to use (based on Ruby framework originally)
* Interfaces well with standard net/http including context.Context

Related:

* <https://sosedoff.com/2014/12/21/gin-middleware.html>
