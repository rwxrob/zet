# Cloud-Native and Kubernetes Colearning, Oct 22, 2021

📺 <https://youtu.be/mnR3QDyA3k0>

* Moving to 2-hour segments
* First five minutes covering goals for session
* Last five minutes wrapping up and summarizing
* Why I don't use/like Docker compose (look into Kompose)
* I went through a moment of Podman (because of `systemd`)
* We need a "host container" image (Dockerfile)
* Overview of `kubeadm init phase --help` for help
* Start of Dockerfile
* Use of `run` shortcut command
* Discovered that `apt-key` is deprecated and will be removed
* Instead copy keys directly to `/etc/apt/trusted.gpg.d`
* Always use `apt-get` in scripts (RTFM to know why)
* Install `systemd` and set `ENTRYPOINT`
* Symlink `/bin/init` to `/usr/bin/systemd`
* Still kinks to work out

Related:

* [20211019143421](/20211019143421/) Staged Approach to Understand How Kubernetes Works
* <https://www.linuxuprising.com/2021/01/apt-key-is-deprecated-how-to-add.html>
