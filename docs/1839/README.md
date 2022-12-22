# Bonzai best practice: high-level API and `Cmd` get separate repos

Following these Bonzai separation-of-concerns conventions ensures that developers avoid problems with missed expectations and problematic versioning and overall support and legal information:

* A Bonzai stateful command branch SHOULD have its own repo
* A Bonzai stateful command branch MUST NOT export anything but `Cmd`
* Bonzai subcommands MUST NOT have a Version, Copyright, License, Site, Source, Issues
* An API imported by a command branch MUST have its own repo
* Go API git repos MUST end with `-go` (ex: `keg-go`)
* Command git repos MUST be the name of the command (ex: `keg`)

There was a time when keeping the high-level API functions was encouraged within a Bonzai stateful command branch repo, but this has proven to have rather glaring problems.

***Git tagging is pretty much one tag per module.*** Mono-repos are thing for some, but they suffer from a rather major failing when dealing with Go code that depends specifically on the version tags of the git repo itself, not the packages under those repos. In fact, I really don't get the logic behind use of mono-repos at all for Go projects. Kubernetes has been bitten by this hard and started moving to separate repos some time ago so that the projects all get their own git tagging and versioning.

***APIs should be stable and change very little.*** An API is "forever". That means that semantic versioning has very specific meaning that no one wants to mess up. In my world, pretty much every API that gets its own repo should be considered backward compatible as much as possible.

***Command documentation pushes versions.*** In a Bonzai branch the version of the command is changing all the time at a different version than the API it depends on. This is particularly true when considering all the changes just for documentation --- especially now that we are moving into the era of `text/*` multi-language code generation.

***Exported commands other than Cmd encourages broken dependencies.*** Initially it seems like a good idea to group a bunch of commands together. Plus, each `Cmd.Version` value can be confusing. The value of each subcommand having the possibility of adding such is nice in case any of those commands grow up into something that could be pruned out into its own branch. But as a rule, only the `Cmd` main command should have any of the following:

* `Version`
* `Copyright`
* `License`
* `Site`
* `Source`
* `Issues`

***Go documentation overlap with command documentation.*** A lot of the API documentation will indeed be duplication of what is written for the end user in the commands themselves, but the audiences are *very* different. Keeping the API as an API means that the generated Go documentation and example tests are available to developers in the expected ways. Developers might be confused by having this stuff along with user documentation in the same place.
