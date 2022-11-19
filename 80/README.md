# Kubernetes `ls -l` Equivalent: `kubectl api-resources`

This dumps everything. At the end of the day, everything in Kubernetes
is implemented as an API, *everything*. Looking through them all, and
isolating with `-n <namespace`. You can learn a lot just by doing this
and using `k explain` on everything.
