# Great Age of the Monolith/Multicall Binary

I believe we are headed into the next age of modular deployment
architectures. First we had virtualization, then we had containers, then
container orchestration. The obvious next step is *not needing Linux at
all*, just a single, monolithic binary that has every possible thing you
would want to do contained inside of it, with a built-in shell that is
statically linked, and can run *anywhere* including in web browsers as
web assembly, big binaries that are themselves tantamount to a small
Linux shell workspace.

Bonzai™ is a framework specifically for taking us into this new era. The
technology exists today to create a single binary that can be copied
around with wild abandon to *any* system and just work. This is a
hackers wet dream, by the way, no tty hassles, who cares about the OS,
just do what I want.

Go is very uniquely positioned in this space. It is as easy to write as
python or bash or perl, but contains amazing power in the standard
library by itself. The `net/http` package alone is enterprise,
high-performance ready, and the encryption options are insane. Go's
concurrency is best of breed, only Erlang is better. Go is seriously the
best tooling language to come to the hacker community since C. (Rust is
a fucking joke in comparison.) But it's not just hackers who will
benefit. All of the operations world will. The very paradigm of
applications development today will dramatically change as the age of
the monolith progresses.

    #predictions #golang #bonzai #monolith
