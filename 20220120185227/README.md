# Vagrant ENV Variables Win Over Vagrantfile

Even if you change the provider in your Vagrantfile if you have the
following set it will override it. I discovered this trying to use
`virtualbox` as a provider to see that all changes to the file were
ignored.

```
export VAGRANT_DEFAULT_PROVIDER=libvirt
```

In my case, it still used libvirt even though I explicitly set
`virtualbox` everywhere. It wasn't until I explicitly set it on the
command line that I saw the error message that I needed.

```
vagrant up --provider=virtualbox
```

This produced the following:

```out
The provider 'virtualbox' that was requested to back the machine
'foo' is reporting that it isn't usable on this system. The
reason is shown below:

Vagrant could not detect VirtualBox! Make sure VirtualBox is properly
installed. Vagrant uses the `VBoxManage` binary that ships with
VirtualBox, and requires this to be available on the PATH. If VirtualBox
is installed, please find the `VBoxManage` binary and add it to the PATH
environmental variable.
```
