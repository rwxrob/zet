# Check for Newer Version

The entire process of checking for a newer version of an app, a
knowledge base (or whatever really) really shouldn't have to be as
complicated as parsing an authenticated REST API just to compare the
latest semantic versions. This might be necessary for many things, but
even more things don't need that at all.

Let's pretend there is no `git`. How would something "phone home" to see
if an update is waiting? The answers are simple and complex. Anciently,
we just kept a VERSION file in the root. It would be compiled into the
program in different ways and was always there to easily check with
basic shell scripts to identify a change. A big advantage of this
approach is that everyone can do it with minimal coding, or no coding
at all.

And what about semantic versioning? Do we really need it?

I'd suggest that most applications really don't care. They just need to
know if something has changed at all.

What if we did a UPDATED file that just had an isosec time stamp? It
seems so simple but would work with or without any other hosting system.
