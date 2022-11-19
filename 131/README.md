# Golang: Accept Interfaces, Return Structs

I first read this little gem in *Learning Go, an Idiomatic Approach to
Learning Go* and I gotta say, that alone was almost worth the \$40 (as
sad as that is to say). I think the advice would apply to any
programming language the supports interfaces. It's pretty simple but
helps avoid a lot of time-wasting gotchas later.

The first one is obvious to most. Passing an interface means that
anything coupled to your implementation of the thing is not in fact
locked to it. That you can change it to be whatever you want any time.
Add methods, remove, who cares. *You* are the only one impacted because
you are doing all the manipulation within your method and only using the
public methods of that interface. (You would never, for example, cast an
argument to some specific struct. That's suicide.) This is the primary value proposition of interfaces in the first place.

The second part, "return structs" was something I missed early on (and
paid the price in complexity). Beginners who discover interfaces
sometimes get overzealous in their use and start *returning* them as
well. But the problem comes later when using the results of those method
calls. By returning an interface (a bad-ish thing) you force everyone
using your methods to use the interface instead of operating directly on
the struct. There are times when this is legit, but more frequently you
want to return something the fulfills an interface, but is returned as
the struct itself.

This issue is really hard to put into words, but when you hit the issues
this resolves (usually after you have tons of code with tons of packages
and subpackages with interdependencies) you appreciate it more.

Jack Lindamood explains that the goal is to maintain a "balance of avoiding
preemptive abstractions while maintaining flexibility."

*[Unfortunately, reading the book doesn't even work in the web Kindle
reader. You can tell that the people who really understand Go are
holding their knowledge tightly behind a paywall these days. But don't
worry, Imma rephrase all of it and make videos and writing about it eventually.]*
