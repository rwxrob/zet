# Writing a Large File Web with Go Safely

No `ReadAll` is not the answer if you don't want to blow up your memory.
Use the `io.Copy()` approach instead.

```golang
import (
  "net/http"
  "io"
  "os"
)
// ...
out, err := os.Create("output.txt")
defer out.Close()
// ...
resp, err := http.Get("http://example.com/")
defer resp.Body.Close()
// ...
n, err := io.Copy(out, resp.Body)
```
    #golang #tips #http
