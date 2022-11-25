# It's Good to Learn Mac UNIX Command Line

Apple Mac computers are the single biggest official UNIX distribution on
the planet and learning how UNIX actually works has significant value.
For example, the following will *not* work on a true UNIX system:

* `mkdir -p path/to/some/dir` - create parent directories
* `grep -P ...` - use `pcregrep` instead
* `sed -i ...` - use `perl -pie` instead

The list is actually much longer than this.

It is absolutely critical that people creating scripts and learning
command-line skills learn the UNIX standard first so that they know when
they are diverting from that standard instead of being surprised one day
when their shit just doesn't work and they don't know the alternative.
Unfortunately, the easiest way to learn this is to buy a Mac and use
it's command line after installing all the GNU core utilities and using
them with their real names (`ggrep`, `gsed`, `pcregrep`, etc.)

This is yet another reminder just how fucking broken most of the
training materials on the Internet really are. The worst part is that
they don't even know it. It is so much more important for infrastructure
engineers to learn UNIX while learning Linux, which, strictly speaking,
is a derivative of it. That way people understand a much broader
landscape of systems not just limited to Mac, but also including all of
the BSD variations, AIX, Illuminos (Solaris), and such that *true*
professionals will eventually encounter in large enterprise environments.

* terminal - How to replace Mac OS X utilities with GNU core utilities? - Ask Different  
  <https://apple.stackexchange.com/questions/69223/how-to-replace-mac-os-x-utilities-with-gnu-core-utilities>

    #rants #education #linux #mac #apple
