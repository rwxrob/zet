# Kubernetes (`kubectl`) Seems to Expect 90 Columns

After recently updating my live-streaming terminal width to 91 I
realized that when running any `kubectl` command that everything looks
wonderful. I haven't read anything official, but piping the headers
through `wc` shows that a `kubectl get po,no -A` comes in at 87 columns.
That has to mean that unofficially the creators of all the Kubernetes
tools are expecting 90 columns minimum. Most people might not care about
that, but knowing this really makes me happy. At least now I know what
I'm dealing with.

Tags:

    #k8s #terminal #settings #kubectl
