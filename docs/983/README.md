# Do not write Go malware from GitHub

This goes without saying, but Go saves the import strings and paths to
the packages with the binaries to enable stack traces (which is no more
insecure than anything Python does, although C does strip this
information).

Related:

* <https://github.com/golang/go/issues/50501>
