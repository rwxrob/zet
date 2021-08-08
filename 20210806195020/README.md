# Kubernetes 'Objects' vs 'Resources'?

> "Furthermore, Kubernetes is built around various primitives referred
> to in the code base as 'Objects'. In the Go programming language, we
> explicitly did not ever build in the concept of an 'Object'." (Kris
> Nova)

Original Kubernetes proof of concept was in Java, which has somehow left
behind this legacy of the object terminology.

They are the same, but "resources" is more accurate (and just cooler,
let's face it, who want to refer to an old Java influence, for
anything). 
