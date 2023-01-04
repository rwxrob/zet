# Use `io.Copy` to "print" debug HTTP requests with Go

Just adding print statements is the number one preferred method of debugging applications (according to a 2021 StackExchange survey, which is sus, of course). Here's an easy way to get a server that just dumps the request itself to standard output so you can run it and just monitor it from another terminal (pane).

```go
func handle(w http.ResponseWriter, r *http.Request) {
  fmt.Printf("headers: %v\n", r.Header)

  _, err := io.Copy(os.Stdout, r.Body)
  if err != nil {
    log.Println(err)
    return
   }
}

func main() {
  log.Println("server started")
  http.HandleFunc("/whatever", handle)
  log.Fatal(http.ListenAndServe(":8080", nil))
}
```
