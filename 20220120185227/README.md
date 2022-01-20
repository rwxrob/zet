# Vagrant ENV Variables Win Over Vagrantfile

Even if you change the provider in your Vagrantfile if you have the
following set it will override it. I discovered this trying to use
`virtualbox` as a provider to see that all changes to the file were
ignored.

```
export VAGRANT_DEFAULT_PROVIDER=libvirt
```
