# Bonzai Shell, Hooks, and Caching

Woke with a rather obvious idea for something that can really make
Bonzai into a shell that has just not yet been made. The idea is
consistent with composition, the main basis for the Bonzai design. It's
simple, create a `Hook` type to go with `Cmd` and `Completer` and
`Configurer`. A hook is just an importable package that hooks into the
execution of each Cmd.Run, Cmd.Call, or Exec. A `Hook` would get all the
arguments passed to each as well as the output from each. A `Hook` could
alter the inputs before they are passed on, or the output before it is
displayed. I hesitate to allow modification of input/output, though,
because knowing what `Hook` messed with the input or output could get
messy. Hooks are how I would implement history. Any number of different
types of history could be created, even combined. Hooks could also allow
the dynamic writing of macro/scripts. A command like `z macro start`
could trigger a hook to start writing each subsequent `z` call to a
macro file. This all needs caching to really be solid. I have to put
some more thought into that.

Caching is the key to getting off of complex single commands with tons
of arguments. It provides a consistent, safe way to preserve state
between simpler command line execution. Setting variables in shell is a
way to preserve that state between command line executions, but what if
we took that one step further, at the cost of a slight bit of
performance. What if we maintained the cache as a Protobuf binary, the
fastest possible thing to load and persist to disk. What would be the
cost in performance? I think it would be negligible. So say we add `z
cache foo everything else is the value` and `z cache foo` fetches the
value from the cache. I really think the delay in reading from the cache
would be really minimal considering it is an interactive session. But
even plans for "macros" or "scripts" would be fine, and more
importantly, have all their variables persisted effectively by using `z
cache` for it.

The obvious next step is to add the `|` operator (and only the pipe
operator) allowing `z` to run in interactive/shell mode where it detects
if the session is interactive and prompts and stuff, and if not, assumes
the standard input is, indeed, a number of `z <command> ...` lines. In
which case something like this becomes a Bonzai script:

```
set foo something here
set bar another value here
somecmd with args | set something
get foo bar | set combined
get combined
```

I think that like `Configurer` we need to provide a `Cacher` that
provides `Get(name string)` and `Set(name, value string)` and
`Clear(name string)` as well as `ReqCache bool` so people creating
commands can ensure those composing their own trees pick a `Cacher` for
their `z` command. Say someone wants to cache to a Reddis database, or
SQLite, or the cloud someplace since they don't even have a filesystem.
All would work. The Protobuf file in `os.UserCacheDir` is just the first
one I would implement.

The really cool thing about that is that by combining hooks and the
ability to process lines macro/script, that users can easily recreate
any natural combination of steps and then edit those steps directly.
This is something the `script` command never actually got quite right.
It always produces files that themselves cannot be run. `z script start`
would, I figure, activate the hook that records every `z` command
thereafter, which its arguments, to a file, text or protobuf, and then
`z script stop` would stop. `z script edit` would open that file with
the `z config editor` and `z script save <name>` would store it in the
`os.UserConfigDir` or someplace similar. `z script run <name>` would
obviously just run that script. And we already have support for aliases
if that is too much to type. But even better, `z script gogen <name>`
could generate Go code that could be plopped rather easily into a `Cmd`
definition in my monolith, so there aren't a bunch of scripts around in
different files and such. I don't know if we should call it a "macro" or
a "script". I feel like "script" is better though, specifically
BonzaiScript which you can learn in five minutes. "It has '|'". The end.
That is all there is to learn. Everything else is something you can
already do with your `z` monolith, whatever those things are. The
"syntax" of the language depends entirely on what you put into your
Bonzai tree.

So the next step is going to be the `bonzai.Cacher` interface and the
first reference implementation using Protobuf stored in
`os.UserCacheDir`. Then we'll probably need a `bonzai.Shell` interface,
or perhaps just `bonzai.Hook`. I don't want this project to get out of
control, but those are the essentials that I've known it would always
need. And I think they cover the bases for all "replace my shell script"
efforts.
