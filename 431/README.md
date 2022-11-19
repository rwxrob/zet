# Only Certain Kubernetes Resources Create from CLI

Just learned the hard way that a PersistentVolume in Kubernetes *must*
have a YAML resource file manifest. There is no other method of creating
it.

This is really too bad because creating one quickly and dumping it
during a dry-run is a great way to cheat instead of memorizing
everything that has to into it.

Related:

* kubernetes - Kubectl : How to create manifest of persistentvolume from command line? - Stack Overflow  
  <https://stackoverflow.com/questions/66283989/kubectl-how-to-create-manifest-of-persistentvolume-from-command-line>
