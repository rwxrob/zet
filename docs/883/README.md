# Add an `init` System to Containers

TL;DR: mount `-v /sys/fs/cgroup:/sys/fs/cgroup:ro` so that your `apt
install systemd` work. You must have `systemd` installed on Ubuntu for
`kubeadm` to work which is what all major Linux distro supporting
Kubernetes require (Ubuntu, Red Hat, SUSE).

I'm still relatively new to creating my own images, but I've been
fascinated by how most images don't have an `init` system of any kind.
PID 1 is always `bash` or something. When working with use cases where
you need to simulate an actual host machine (which I call a *host
container* or *workspace container*) then you really do. But do you
really need to bring the big, ugly, bloated `systemd` piece of shit into
your container to model a host OS?

The answer is no. But there are a lot of options to pick from. Narrowing
it down has been non-trivial. Not all `init` systems are created equal,
and many are simply not detected by things like `kubeadm` as sufficient. Here is a list I'll maintain as I uncover different alternative options and test them:

* `openrc`
* `sysvinit`
* `upstart`
* `tini`
* `runit`
* `nosh`
* `finit`

Since I'm almost always doing this for Kubernetes related work for me
the choice became obvious once I read through the `kubeadm` source code
to figure out which "init systems" are supported. `systemd` and `openrc`
are the only options, and since they pulled `openrc` support from Ubuntu
the answer is forced on us: get `systemd` to work (which is not trivial,
unfortunately).

```go
// GetInitSystem returns an InitSystem for the current system, or nil
// if we cannot detect a supported init system.
// This indicates we will skip init system checks, not an error.
func GetInitSystem() (InitSystem, error) {
	// Assume existence of systemctl in path implies this is a systemd system:
	_, err := exec.LookPath("systemctl")
	if err == nil {
		return &SystemdInitSystem{}, nil
	}
	_, err = exec.LookPath("openrc")
	if err == nil {
		return &OpenRCInitSystem{}, nil
	}
	return nil, fmt.Errorf("no supported init system detected, skipping checking for services")
}
```

> ⚠️
> Be sure to disambiguate your search for "init systems" from "init
> containers" which are an entirely different thing in Kubernetes.

Related:

* When not to use docker run \--init - Stack Overflow  
  <https://stackoverflow.com/questions/56496495/when-not-to-use-docker-run-init>
* Docker and systemd \| The Startup  
  <https://medium.com/swlh/docker-and-systemd-381dfd7e4628>
* When not to use docker run \--init - Stack Overflow  
  <https://stackoverflow.com/questions/56496495/when-not-to-use-docker-run-init>
* 3 Fixes for System Has Not Been Booted With Systemd as Init System  
  <https://www.partitionwizard.com/partitionmanager/system-not-booted-with-systemd-as-init.html>
* GitHub - Yelp/dumb-init: A minimal init system for Linux containers  
  <https://github.com/Yelp/dumb-init>
* Alpine Replacement for OpenRC
  <https://skarnet.com/projects/service-manager.html>

Tags:

    #k8s #docker #init #systemd
