# Hashicorp vault uses complete -C

When searching for how to enable Hashicorp completion I noticed that the practically undocumented `--autocomplete-install` hidden option only adds the same `complete -C vault vault` to the `.bashrc` or `.bash_profile` just like my Bonzai CLI framework does. There is a user-contributed zsh completion script, but it is minimal. The `vault` tool uses Hashicorp's own CLI framework, which is only slightly better than Cobra but demonstrates that when developers care, they tend to hate Cobra.

Discovering this has emboldened me to continue to built and support Bonzai and to come up with a way to dump tab completion scripts for `zsh`, `powershell`, and `fish`. Once added, there will be nothing holding any rational tool developer from using it. (Anyone who actually thinks `-` and `--` options anywhere on the command line is a good think is just not thinking rationally.)
