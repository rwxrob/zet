# Torn between providing in-command docs over stand-alone keg

I spent a lot of time making bonzai brilliant for including very readable, rich documentation that didn't need to be installed separately, but now I'm experiencing a rather pleasant dilemma: where to write the docs in the first place?

The command itself cannot be used for KEG Web sites. It requires the command be executed.

I wonder if I could add a keg generator to bonzai `help` command. I mean, we have access to all the code and the AST from all the internal help documentation. I could make a `help render keg` command that could output or overwrite a target keg path. Then, it could be rendered with keg tools or whatever, or perhaps not, perhaps it is just written to `docs` and it is a webified version of the docs that anyone can read on Github Pages once activated, which I also need to write into `keg` since it can be done entirely from the GitHub API.

My inclination is to maximize how easy it is to write command documentation in a bonzai branch command itself, and do all the other generation from it. We want to facilitate drop-dead simple user documentation otherwise command authors just won't write it. I know. I still have more to write.

If we do this right, we could even have a PDF document generator from the composite of help documentation so anyone could actually print the documentation for any bonzai stateful command tree. That's the holy fucking grail right there.
