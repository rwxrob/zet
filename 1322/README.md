# Source `/etc/bash_completion` as `root` to Fix Tab

If you run into the following error as `root` having sourced the
completion stuff for `kubectl`, `kubeadm` and company then you might
have to source `/etc/bash_completion` to get the function that it needs
(which is sourced automatically for all users on the system except
`root`).

```
╔ rwxrob.tv:lab-k8s-hard-way-docker(main)
╚ $ d run -it --rm lab-k8s-hard-docker-control bash
root@066816ab811d:/# . <(kubeadm completion bash)
root@066816ab811d:/# kubeadm bash: _get_comp_words_by_ref: command not found
root@066816ab811d:/# . /etc/bash_completion
root@066816ab811d:/# kubeadm
certs       config      init        kubeconfig  token       version
completion  help        join        reset       upgrade
```

Tags:

    #tips #bash #k8s #completion #linux
