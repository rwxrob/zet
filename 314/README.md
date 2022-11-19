# New `config` Package with Structure

All the configuration stuff I've built in the past has been flattened
for simplicity into Redis-like key-value pairs, but that has always
struct me as an unnecessary limitation. I want my new Bonzai defacto
standard config (which is maintained as a Bonzai sub-package like
`help.Cmd`) to be able to use complex configuration files, but how to
create an easy way to write and read from it? I know I want some method
of pathing as `jq` supports. I wonder if I can pass a struct and have it
use reflection to get the structure. Go is too rigid to allow people to
just change things up. I keep thinking of how Kubernetes does this. For
the most part K8S has you change the file rather than try to change
individual values (although you can), and just using `jq` to get the
values is probably better than anything else. I suppose if an
application needed to change the configuration file it could use its own
struct and just use the `config` Bonzai branch to find the file to use,
lock it, and such. The `config` package could also just pass stuff to
`jq` for now to be able to query the values easily until I can port the
main parts of `jq` over to Go.
