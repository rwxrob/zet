# Bonzai Cmd Variable Naming Standard

Since Bonzai commands (Cmd) are intermixed with the other exported
identifiers of the high-level module, most of which will have nothing to
do with Bonzai, it makes sense to always qualify the special Bonzai
Cmd variables, public and private, with the `Cmd` suffix. Of course, the
main entry point branch will be just `Cmd` by itself.

    #bonzai #golang #standards
