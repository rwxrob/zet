# Vagrant 3.0 Ported to Go, But ...

Hashicorp is porting Vagrant to Go, which is nice because our Fluff
project is all in Go for what I assume are the same reasons. But Vagrant
still has a lot of the old technical debt that we are overcoming with
Fluff:

* It's ancient (lots of technical debt)
* It adds layer of unnecessary abstraction
* It wasn't conceived with `cloud-init` in mind
* It doesn't play nice with WSL2
* It has a screwed up network model
* It isn't a single executable
* It's in Ruby

* <https://twitter.com/mitchellh/status/1403400750311505924?lang=en>
