# Conventional Bonzai Branch Releases

I'm trying to create a conventional approach to creating binary
artifacts from Bonzai branches and commands for release in a way that is
consistent enough that I could codify it in `update` and `bonzai
release`. Creating all the different binaries for all supported devices
isn't so much the problem, what is the problem is getting the artifacts
into the release section of GitHub and having them named properly.

Most people would use a GitHub Action for this, but I can't. You cannot
be sure you have GitHub Actions. We don't have them at work (or at least
they are not supported). So the `bonzai release` command is going to be
really key here. It also needs the ability to observe release
configuration information in a conventional way so that we can isolate
the architectures. And there isn't going to be any `Makefile`.

So having looked at the Kind project it's clear that they just push all
the binaries for their supported architectures up to the release and
create a nice release document for it as well. I think that is where I
should focus attention, on creating an improved, convention `release`
Bonzai branch that I can build into `bonzai` itself.

    #bonzai #binaries #release
