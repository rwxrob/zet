# Bash Enterprise Cloud-Native Script Sweet Spot

I am realizing today that Bash has specific value for rapid enterprise
scripting. Been tasked with writing a quick namespace script that will
do a Helm 2 to 3 upgrade and finding all the learning I did with Bash to
be coming in handy. Here's why:

* The people on this team *know* shell scripting
* People on this team do *not* know Perl (unfortunately)
* They can figure out Bash-isms far easier than Perl
* POSIX shell is far too limiting and would delay delivery
* This project has zero need for extensive Unicode regular expressions
* Python is to verbose and annoying and requires Python installation
* Bash *can* be placed in Dockerfiles if it is on the base image

The biggest deciding issue for this day is that the person sending the
task to me actually wrote pseudo-code that is already essentially in
shell. These people think in shell about their tasks, with a bit of
Python. Once upon a time they would all *think* in Perl, but those days
have (unfortunately) passed. Bash is king, for today. (I wonder what
they would do if I wrote it in Node, lol.)

This puts Bash in the ultimate sweet spot for creating such things. I'm
happy to see that my beloved Bash-isms (that I have a hard time
isolating from POSIX, which is what `shellcheck` is for). 

For what it's worth, this is exactly what Google does internally (and has
for years). Google has created one of the best shell scripting style
guides I've found.
