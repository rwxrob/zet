# Use `vagrant ssh-config` for `~/.ssh/config`

Sometimes using `ssh` is just more intuitive and *real* than using
Vagrant. The fastest way to do this is to open up `~/.ssh/config` and
use the filter command (`~`) to replace a line with the output of
`vagrant ssh-config 2>/dev/null`. Depending on your changes to your
configuration you might have to rerun this after running `vagrant up` or
`provision`.
