# Bonzai is Becoming What I Have Always Wanted

When you are an operations engineer (or a hacker) and are constantly
putting out fires (or starting them) you need to make high-quality code
very quickly. The term "rapid applications development" seems not only
too formal, but just fucking stupid when you try to describe the demands
of a full-time (on or off the clock) hacker/engineer. That's why
mastering vi/m and bash scripting are so very critical. If Go is to be
viable in that space creating Go applications as quickly and easily as
shell scripts needs to become the norm. And, I'm happy to report that
I'm vary close to accomplishing that. Even more fun is the fact that
BPEGN will allow things to be done rapidly that bash (or even
Python/Perl/PowerShell/Ruby) cannot even dream of doing. It allows the
rapid creation of understandable, clear, grammar parsers without the
complications and performance hit of regular expressions. It's beautiful
that the name of the core method is `scan.Expect` because that is what
it has become, a replacement for many of the uses of `expect` before.
Now that I've added `scan.Hook` types people can embed event handling
directly into their `Expect` expression streams. It's just a matter of
time before I have all of the standard PEGN syntax ported one-for-one
with a BPEGN expression so that tools like `bonzai pegn` will be able to
dump full expressions without leaving my vim session. Hell, it's even
easier to write BPEGN than PEGN itself. I'll definitely need to work on
a BPEGN -> PEGN converter as well in order to create documentation.

* <https://github.com/rwxrob/bonzai>

    #linux #golang #sre #devops #coding
