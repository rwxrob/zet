# Use Directories with Bonzai Monoliths

When creating branches within your monolith it can get messy in there
with everything in the top level. After all, you started using a Bonzai
management approach to avoid a bunch of annoying shell scripts that have
to be in the same directory. So here are the rules I've been following:

* Every branch get's its own repo or directory
* Every branch gets a `name.Cmd`
* Branches can decide to have `name.OtherCmd` exports
* Most branches will have `name.privCmd` subcommands
* Always use `Cmd` in the name to easily find them

    #bonzai #tips #coding #golang
