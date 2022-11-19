# New Way to Add Extra Drive with Vagrant VirtualBox

The easiest way is also "experimental" and only works with the
`virtualbox` provider. First `export VAGRANT_EXPERIMENTAL=disks` (or add
to your `~/.bashrc`). Then create a Vagrantfile that looks something
like this.

```ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

# MAKE SURE TO `export VAGRANT_EXPERIMENTAL=disks`

Vagrant.configure("2") do |config|
  ["control","worker1","worker2"].each do |name|
    config.vm.define "#{name}" do |node|
      node.vm.box = "generic/alma8"
      node.vm.hostname = "#{name}"
      config.vm.provider "virtualbox" do |vb|
        vb.cpus = 1
        vb.memory = 1024
      end
      node.vm.disk :disk, size: "10GB", primary: true
      if name == "control"
        node.vm.disk :disk, size: "10MB", name: "extra" # small, so can fill
      end
      node.vm.provision :shell, path: "provision", keep_color: true
    end
  end
end
```

>⚠️
> When doing it the *old* way, make sure to use 'IDE Controller' when
> working with Linux.

Related:

* <https://www.vagrantup.com/docs/disks/usage>
* Vagrant - Adding a second hard drive - EverythingShouldBeVirtual  
  <https://everythingshouldbevirtual.com/virtualization/vagrant-adding-a-second-hard-drive/>
* [20220121013105](/20220121013105/) Learning Lab: Vagrant Local `kubeadm`

Tags:

    #linux #vagrant #devops #coding #vms
