# Don't Forget `--dry-run=client` When Creating YAML Files

The easiest way to create YAML resource manifest files is to just create
them using `kubectl create` and output the YAML into a file that can
later be applied. But, be sure to add `--dry-run=client` so that you
don't *actually* create the resource yet. This is especially important
when dealing with resources that could take a very long time to deploy
or delete later.

Tags:

    #k8s #tips
