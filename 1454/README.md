# Bonzai Shell will be `bonsh.Cmd`

I do like the name `bonsh`. That will be the command that starts an
interactive REPL or just processes all of its arguments as a single line
of bonsh shell code. Technically, if will be the `shell` subcommand of
the `bon` branch but `shell` will be the default subcommand (instead of
`help`). This an then be made into a shortcut in the composing tree as
`z shell` or `z sh`. (I don't give a shit about `zsh` confusion, which
is a dangerously stupid shell that no one should ever use.)

* `-` - inline separator
* `\r?\n` - also inline separator

I'm going to heavily steal from the best of Perl contextual variables.
The `bon.Shell` will maintain a central buffer that is sent to the
standard input of any command in the list separated by the command
inline separator (dash, `-`).

For example, the subcommand `load` of the `bon.Shell` command would fill
that buffer and that's it.

```sh
z sh load foo.txt - prefix someprefix
```

This is the exact equivalent of the following shell command but does not
rely on any specific shell implementation. The Bonzai command *is* the
shell.

```sh
z prefix someprefix < foo.txt
```

And if it concerns you that I'm loading everything into memory, consider
that another subcommand could be written to send each line, one at a
time.

```sh
z sh each line foo.txt - prefix someprefix
```

Or, say you want to handle each UNICODE codepoint one at a time.

```sh
z sh each rune foo.txt - prefix someprefix
```

And since UNIX/Linux has turned everything, everywhere into a file, we
can use the command to open files that are sockets, pipes, or whatever.
In fact, the only thing needed on the device is a filesystem that is
supported by Go.

The beauty of Bonzai is that it is entirely modular, just like the best
principles of the UNIX philosophy. In fact, I'm just ripping off the
UNIX philosophy and "filters" design principle and putting it all into a
single monolith command, which seems against the UNIX way, but it really
isn't if you consider that any Bonzai composite tree *is* UNIX (in a
way). I mean that. All GNU/Linux/UNIX commands will eventually make
their way into Bonzai trees and can be composed into a *single* monolith
that can go anywhere. At that point we won't just have "Bonzai Linux",
we'll have something outside the boundaries of both UNIX and Linux, an
entirely different paradigm of monolith modularity to rival
virtualization and containerization before. The binary *is* the distro
(much like BusyBox championed all those years ago.). We don't even care
what the operating system is at all. Let me say that again, WE DO NOT
GIVE A SHIT ABOUT THE OPERATING SYSTEM OR ARCHITECTURE! ('cuz Go). This
will revolutionize tools development in general once it catches on. 

I really am going to need to write an O'Reilly/Manning book just about
Bonzai before hitting the conference circuit with it in 2023. I'm now
shooting for Bonzai v1.0.0 on Christmas 2022.

    #bonzai #shell
