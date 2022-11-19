# Discovered Better `os/exec` from Kubernetes Project

Digging through the `kubeadm` code (while seeking a better understanding
of what is happening *exactly* during the "phases") I ran across a
wonderful little replacement to the standard `os/exec` package that
allows the use of mockups during testing:

     This package provides an interface for `os/exec`. It makes it
     easier to mock and replace in tests, especially with the `FakeExec`
     struct.

It was a little hard to find given how buried the source was under
`.../vendor/k8s.io/utils/exec` inside the main `kubernetes` source, but
the import is pretty easy. I found it seeing `execer` all over in the
code for running thing command-line like things easily. It seems like
all the Kubernetes `cmds` use it, and for good reason. Here's what an
import looks like:

```go
import (
    utilsexec "k8s.io/utils/exec"
)
```

This reminds me how valuable reading through the Kubernetes source code
--- including all the utilities --- is for learning and getting ideas
(and always has been).

Related:

* <https://github.com/kubernetes/kubernetes>

Tags:

    #k8s #golang #exec #tips #coding
