# Another Reason to Hate Cobra (`exec bash`)

Looks like the completion functions that come out of Cobra are the
reason I cannot add simple shortcut completion that can withstand `exec
bash` or `sourc ~/.bashrc` changes.

A common technique to create shortened versions of certain commands that
will work everywhere (aliases will not) is to export a function or
create a one-line `exec` script.

```
k() {
  exec kubectl "$@"
} && export -f k
```

Or, if you prefer (and you probably should so you can use `k`
even from programs that call `exec` system calls):

```
#!/bin/sh
exec kubectl "$@"
```

To add completion the common method is to look up their long forms with
`complete` and add them to `~/.bashrc` with the short form:

```
$ complete | grep kubectl
complete -o default -F __start_kubectl kubectl
echo complete -o default -F __start_kubectl k >> ~/.bashrc
. ~/.bashrc
```

At first this seems to work (when you source the script after adding
it):

```
$ k <TAB><TAB>
annotate       completion     drain          logs           scale
api-resources  config         edit           options        set
api-versions   cordon         exec           patch          taint
apply          cp             explain        plugin         top
attach         create         expose         port-forward   uncordon
auth           debug          get            proxy          version
autoscale      delete         help           replace        wait
certificate    describe       kustomize      rollout        
cluster-info   diff           label          run   
```

When you confirm the `complete` entry everything looks fine:

```
$ complete |grep kubectl
complete -o default -F __start_kubectl kubectl
complete -o default -F __start_kubectl k
```

This will sometimes work with *new* shells and windows and other times
it won't, which makes it *very* frustrating when you discover the
problem later. When it doesn't work you can see that something failed
with the `k` completion:

```
$ complete |grep ' k'
complete -F _minimal k
```

Where did that even come from? I still don't know. But my suspicion is
the Cobra completion function. Then if I source it again.

```
$ . ~/.bashrc
$ complete |grep ' k'
complete -o default -F __start_kubectl kubectl
complete -o default -F __start_kubectl k
```

Looks good, right?

But as demonstrated below, this blows up with the completely inoccuace
and common `exec bash` to reset and replace the current bash shell with
a new one. Doing this with a shortcut that calls the 

```
$ k <TAB><TAB>
k _get_comp_words_by_ref: command not found
_get_comp_words_by_ref: command not found
```


