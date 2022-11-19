# Golang `init` Modules

For lack of not just a "a better" term --- but *any* term --- I have
chosen the term "init modules"  as the moniker for all modules
(technically packages) that are imported just to get the side effects
that happen when the collective `init()` functions of the imported files
of the module package are executed during the import process (something
that is unique and beautiful to Go). Pretty much every database driver
is an *init module* (as in, "the PostgreSQL database `init` module") as
all all [CmdBox] modules. A CmdBox "tool" is synonymous with CmdBox init
module.

[CmdBox]: <https://github.com/rwxrob/cmdbox>
