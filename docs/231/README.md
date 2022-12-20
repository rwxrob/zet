# Use `net/http/httptest` for HTTP Go Testing

No need to start up a full web server to test web client code in Go.

```go
	// setup mock web service
	handler := http.HandlerFunc(
		func(w http.ResponseWriter, r *http.Request) {
			fmt.Fprintf(w, `{"word":"hello","name":"Rob"}`)
		})
	svr := httptest.NewServer(handler)
	defer svr.Close()
  // then use svr.URL for everything
```

And to set the status

```go
     w.WriteHeader(http.StatusBadRequest)
```

* Golang httptest Example  
  <https://golang.cafe/blog/golang-httptest-example.html>
* Testing Golang With httptest - DZone  
  <https://dzone.com/articles/testing-golang-with-httptest>
