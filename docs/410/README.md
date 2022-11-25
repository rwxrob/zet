# Inclined to Go Back to YAML

After discovering `inline` support in gopkg.in/yaml.v2 I'm having a
really hard time not using only YAML for everything. None of the JSON
stuff has anything like it, I mean, *nothing* like it. And since JSON is
valid YAML there is really no reason not to use the gopkg.in/yaml.v2 for
everything related to configuration that is saved anywhere. That's
probably why the Kubernetes project has hard-coded v2 into everything
and has no desire to go with v3, ever.

Of course, this means that I'll need to rewrite `conf-go` and make it
`config` instead and turn it into a Bonzai branch. The reason I went
with `conf-go` keeping everything on a single line was because it is
more "UNIX-ey", but my recent feelings about moving to monoliths with
subcommands makes all of that sort of out-dated thinking (and I really
mean that). There are many aspects of the old UNIX philosophy that just
don't hold water today, otherwise we'd still be dynamically linking shit
and stuff like that.

And let's fact it, like it or not, YAML has won the configuration file
wars. It is so dominant in everything these days that displacing it is
silly to even contemplate. TOML certainly doesn't have a prayer. Wish
I'd known about `>-` in YAML before getting so into TOML (and making
their logo, lol).

    #yaml #json #toml #configuration
