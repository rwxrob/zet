# Going to Create John the Distributed Ripper

One of the tools I've been wanting to get back into is brute-force
crackers like John the Ripper, but at a larger scale. I want to make one
that I can use to distribute across multiple Kubernetes nodes and
leverage GPU power of them as well so that they are all working
concurrently on different sections of the dictionaries, a distributed
Ripper. It's a tool that could seriously benefit from the power of an
average home lab these days. Not everyone has the money (or desire) to
do such work in *any* cloud where you can dial up the MIPS. Plus I
really want to see how to schedule such work on the GPU if one is
detected.
