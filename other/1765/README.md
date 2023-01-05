# Torn between providing in-command docs over stand-alone keg

I spent a lot of time making bonzai brilliant for including very readable, rich documentation that didn't need to be installed separately, but now I'm experiencing a rather pleasant dilemma: where to write the docs in the first place?

The command itself cannot be used for KEG Web sites. It requires the command be executed.

I wonder if I could add a keg generator to bonzai `help` command. I mean, we have access to all the code and the AST from all the internal help documentation. I could make a `help render keg` command that could output or overwrite a target keg path. Then, it could be rendered with keg tools or whatever, or perhaps not, perhaps it is just written to `docs` and it is a webified version of the docs that anyone can read on Github Pages once activated, which I also need to write into `keg` since it can be done entirely from the GitHub API.

My inclination is to maximize how easy it is to write command documentation in a bonzai branch command itself, and do all the other generation from it. We want to facilitate drop-dead simple user documentation otherwise command authors just won't write it. I know. I still have more to write.

When I first conceived bonzai embedded files where not really a thing. Now they very clearly are a huge thing in Go. In fact, they are one of the biggest reasons to select Go for tools development. I can work out a new longer syntax for `Description` (for example) and write it entirely into the `docs` directory as a Go template in a non-integer node that matches the command names. Then I just embed those strings and assign them to the descriptions directly. That would mean all the editing of the documentation would take place in the `docs` directory, with template files that have full syntax highlighting and such, instead of dealing with writing it within the `Cmd` itself. That approach also frees documentation writers from conflicts with the `cmd.go` file that the core developers would be working with a lot. This definitely sounds like the right way to go. Just have to make it so that bonzai command template documentation can live in a keg without violating the other rules of a keg, which I think we can do with **named nodes** rather than **integer nodes**.

If we do this right, we could even have a PDF document generator from the composite of help documentation so anyone could actually print the documentation for any bonzai stateful command tree. That's the holy fucking grail right there.
