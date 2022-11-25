# Potential Bonzai Repo Package Naming Conflict

As I thought through my personal preference for Go code organization I
started to uncover a potential problem with that organization going
forward (for me and others). It boils down to the dilemma of making
repos themselves into Bonzai branches. The imports are beautiful, but
this forces the high-level functions someplace else (currently `pkg`
which I'm now thinking might need to be `lib` instead). But it's the
naming of the repo itself that I'm cautious about.

For example, `rwxrob/json` is a thing, but what is it? I've just burned
a very important repo name that someone else might also want to use when
doing forks and such. GitHub forking takes care of the renaming to
something else, by the way. Everything is fine as it is because the name
of the repo is not the same as the Go import name, which `vim-go` and
others automatically alias correctly in the `imports`.

But would it be worth it to add another `z` directory convention? This
would free the top level to be whatever people wanted, but forces
everything to use `z` in the import path.

As of today, I don't see any reason to change. People can name the repo
whatever the fuck they want and use the alias so that their Bonzai trees
with `Cmd.Commands` composition look pretty. Besides, inevitably people
are going to want to compose two different Bonzai branches with
identical names, which is why Bonzai composition is so brilliant. It
just allows them to alias things like any other module import.

So I think we are good, but I will continue to put high-level library
stuff into `pkg`. Besides, people coming to the repo will immediately
see the practical benefit and application of those libraries, which is
the whole fucking point, so that *should* be show-cased.

* [20220414094051](/20220414094051/) Personal Preference for Go Code Organization

