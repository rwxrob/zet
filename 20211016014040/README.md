# Cloud-Native and Kubernetes Colearning, Oct 15, 2021

📺 <https://youtu.be/F7xEyfLYrBw>

* Researched certificate creation and management
* Wondering which `easyrsa`, `openssl`, or `cfssl`?
* `easy-rsa` is an OpenVPN co-project
* `easy-rsa` is *literally* a shell script wrapping `openssl`
* Discovered that Kubernetes itself uses `easyrsa`
* `cfssl` is Go using the `openssl` library
* `cfssl` is never installed by default
* `openssl` has been the gold standard since 1999
* `openssl` doesn't use JSON, etc. (uses INI format)
* Decided to use `openssl` (instead of `cfssl` in "tutorial")
* Couldn't figure out `CLUSTER_IP`
* Decided to regroup and try with just `kubeadm` certs tomorrow

Found this fun snippet in the `kubnernetes` source:

    cluster/gce/util.sh:# TODO(roberthbailey): Replace easyrsa with a simple Go program to generate

Related:

* <https://blog.cloudflare.com/introducing-cfssl/>
* <https://www.openssl.org/>
* <https://github.com/openvpn/easy-rsa>
