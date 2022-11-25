# Use `net/http/httptest` for HTTP Go Testing

```go
	// setup mock web service
	handler := _http.HandlerFunc(
		func(w _http.ResponseWriter, r *_http.Request) {
			fmt.Fprintf(w, `{"word":"hello","name":"Rob"}`)
		})
	svr := ht.NewServer(handler)
	defer svr.Close()
  // then use svr.URL for everything
```

* Golang httptest Example  
  <https://golang.cafe/blog/golang-httptest-example.html>

    #golang #http #mock #testing #tips
