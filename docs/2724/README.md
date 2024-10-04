# Only way to safely change TOML value in-line is python

```python
#!/usr/bin/env python3

import toml
import os

with open("/etc/containerd/config.toml","r") as t:
    conf = toml.load(t)

conf['plugins']['io.containerd.grpc.v1.                                            cri']['containerd']['runtimes']['runc']['options']['SystemdCgroup'] = True

pid = os.getpid()

with open(f'/tmp/config-{pid}.new.toml', 'w') as f:
    toml.dump(conf, f)
```

Related:

* Handling TOML files using Python - GeeksforGeeks  
  <https://www.geeksforgeeks.org/handling-toml-files-using-python/>
