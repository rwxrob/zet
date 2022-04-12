# Need to Factor `comp` Out of Bonzai

...if for no other reason than versioning alone. When I add a new
completer to the library I would have to up the version of `bonzai`.
That's just stupid.

God, can I just be done with Bonzai, already? I got shit to do/make with
it.

I want the `bonzai` package to get so fucking boring that it almost
never changes (like the TCP/IP RFC, or JSON/YAML standards).

There's another reason. GitHub and Go documentation already
show dependencies between libraries. So I could look at
`rwxrob/comp-standard`, for example, and see how popular a particular
completion library is, and manage all of its life independently from the
entire fucking `bonzai` branch.

Why the *fuck* does anyone think having a monorepo of everything
developed at a company is a good idea? It's just not. It's just fucking
not.

Arg, okay, here comes another minor version update.

    #golang #coding #rants #bonzai
