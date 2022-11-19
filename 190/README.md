# Vagrant Gives VMs Same IP *and* ARP Address

There is a CentOS/RedHat but in the Vagrant image that forces them to
all have the same Mac and IP. Add the following to Vagrantfile:

```
config.vm.base_mac = nil
```

By the way, this is not a RedHat issue, it's a Vagrant RedHat *image*
issue.

Related:

* <https://serverfault.com/questions/648503/vagrant-duplicate-ip>
* <https://github.com/hashicorp/vagrant/issues/6456>
* <https://github.com/hashicorp/vagrant/issues/9200#issuecomment-409408228>

