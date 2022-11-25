# On the Verge of Creating Own Template Language

It all started with not being able to the backticks in BonzaiMark
Description sections because Go backticks don't have any way to escape
them, which is fine because that makes the entire thing into an
inline-able string by the compiler, so I'm down. But, it caused me to
ask the question, what do these things actually mean? Should I be using
`**foo**` for my command names?

And then, boom, "This shit is all semantic!"

I never recovered from that a-ha moment. I *have* to make it now. The
`{{name}}` becomes the easy version of the `{{.Name}}` and stuff like
`{{cmd "var"}}` can now be used by different template renders to produce
links to that other command documentation once we get this into Web and
PDF form. In fact, once we move beyond just dumping help information to
standard output we can actually have shit link to other things and be
able to tab through it. And, of course, this means our own
implementation of a text-based web-like browser, an eventual Lynx
replacement. (Yeah, my head is exploding at this point.)

So what *are* the things of our system? What are the template commands
that we eventually need? I need to get this shit down before too many
people create their own Dynamic FuncMaps with conflicting (overriding)
names and syntax. PHP, here we come. (This is exactly how PHP got
started, as a template language.)

There are these that are mostly there already:

* `{{exepath}}` - full path to the executable file
* `{{exename}}` - name of the executable without suffix
* `{{execachedir}}` - `os.UserCacheDir` + `exename`
* `{{execonfdir}}` - - `os.UserConfigDir` + `exename`
* `{{cachedir}}` - `os.UserCacheDir`
* `{{confdir}}` - - `os.UserConfigDir`
* `{{homedir}}` - - `os.UserHomeDir`

And these are transformative:

* `{{indent n}}`

But these would be the semantic additions:

* `{{cmd "foo"}}` - reference and potential like to peer or subcommand
* `{{param "foo"}}` - reference and potential like to param
* `{{arg "foo"}}` - present foo as the name of a possible argument
* `{{argv "foo"}}` - present foo as a literal argument
* `{{args 1}}` - actual command argument used (starting at 0)
* `{{cmdline}}` - entire command line as string
* `{{pkg "net/http"}}` - importable Go package
* `{{cmdfields}}` - all the command fields

I do like this because it leave, *italic*, **bold**, and
***bolditalic*** to match their HTML semantic definitions as rhetorical
devices with no other meaning.
