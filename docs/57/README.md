# How NOT to Lock a File in Go

Looks like Go might finally get robust file-level locking available at lease in the `/x` source code. https://github.com/golang/go/issues/33974

I discovered it while working on my `fs` little package and realizing there is no good file locking library out there. In fact, I found a ton of shit including stuff in the main Kubernetes source.

So many seriously bad implementations of file locking exist. None of them take into account the potential race condition of just looking for the existence of a file (this ain't Windows). The proper way to do it is to flock the file in addition to checking if it exists.

Here's an example of a [failed lock design](https://github.com/kubernetes/client-go/issues/1073) that is all throughout the Kubernetes code base (and Kind decided to copy it). Any seasoned UNIX systems developer will immediately see the failures here:

```go
package kubeconfig

import (
	"os"
	"path/filepath"
)

// these are from
// https://github.com/kubernetes/client-go/blob/611184f7c43ae2d520727f01d49620c7ed33412d/tools/clientcmd/loader.go#L439-L440

func lockFile(filename string) error {
	// Make sure the dir exists before we try to create a lock file.
	dir := filepath.Dir(filename)
	if _, err := os.Stat(dir); os.IsNotExist(err) {
		if err = os.MkdirAll(dir, 0755); err != nil {
			return err
		}
	}
	f, err := os.OpenFile(lockName(filename), os.O_CREATE|os.O_EXCL, 0)
	if err != nil {
		return err
	}
	f.Close()
	return nil
}

func unlockFile(filename string) error {
	return os.Remove(lockName(filename))
}

func lockName(filename string) string {
	return filename + ".lock"
}
```

    #golang #coding #rants #filesystem #locking
