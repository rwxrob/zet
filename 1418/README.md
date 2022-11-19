# New Improved `conf-go` Module (Without JSON)

Just finished and released version `v1.0.1` of `conf-go` that uses the
same configuration convention I have been using in the
`template-bash-command` that only uses simple key=value pairs, one per
line, and is far easier to maintain and parse. This will open the door
to recoding all my other dependencies on `conf-go` for their localized,
user-land configurations. The first one will be `cmdbox-config`, which
is embedded into every CmdBox-related tool I have. Next will be
`auth-go`, which really needs better documentation even though I
absolutely depend on it for all my bash script Oauth interactions.

Related:

    * <https://github.com/rwxrob/conf-go>

Tags

    #golang #coding #config
