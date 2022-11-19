# Go Generics Still Worry Me

I agree with ever point made in this [post] about generics. I *really*
love his point about Go dependency management and modules. I did not
know it was "just one man" and now it totally makes sense. The initial
Go module implementation was absolute shit that got rushed out without
any interaction or input from the community. Had there been more time,
massive flaws like `replace` getting committed into production code
would have been avoided in the initial design. 

I am really trying to keep an open mind, but I keep reading people
already planning on changing elements of the standard library to use or
require generics. I just feel like we are being forced to use them
because they *will* bring instability and bloat to the runtime, no
matter how well coded they are. The people who are the most excited
about generics frequently seem to not be that versed in Go programming
in general. They are waiting for them before coming to the language at
all, putting their line in the sand before they'll access Go as a real
language despite the dominance of Go in the most important part of the
tech sector, Docker and Kubernetes native computing.

[post]: <https://1pkg.github.io/posts/golang_dead_end_generics_journey/>
