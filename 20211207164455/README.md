# Get Latest Released Version from GitHub with Bash

In the following example `kubernetes-sigs` is the GitHub account and
`node-feature-discovery` is the repo. Change to whatever you like.

```bash
curl -sSL https://api.github.com/repos/kubernetes-sigs/node-feature-discovery/releases/latest | jq -r .name
```

Tags:

    #linux #github #bash #curl #git #tips
