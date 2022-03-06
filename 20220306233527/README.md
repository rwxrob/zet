# Rust Insists You Just "Trust" Their Compiler

Anyone involved with security will immediately appreciate this irony.

There's been only minimal effort by the Rust team from the very
beginning to provide the source code of the Rust compiler. You have to
have a Rust compiler to compile a new one, which means you can never
trust anyone asking you to compile Rust. There has been an effort with
`mrustc` to be more transparent about all of this, but, of course it is
completely ignored by the Rust evangelists when they state how "safe"
their language is. Remember, this is a language that has willing and
openly stated --- by it's core team leaders who don't even follow their
own code of conduct (according to the "mod team" who resigned in
disgust) --- that "Rust is and always will be political." What is Rust
decides to sneak in a backdoor (if they haven't already)? There is no
fucking way to know if they did or didn't. 

In contrast, Go has a pristine compiler source pedigree that can be
traced all the way back to its original compilation from C (which itself
has been trusted by millions at this point). The Go compiler was create
by some of the most trustworthy individuals in tech history, Thompson
and Pike to be precise.

It really is no surprise enterprises just do *not* trust Rust for core
infrastructure applications and components, and they never will, and you
shouldn't either. Rust is, at best, a play language with some
interesting concepts that will influence other languages that matter,
like Go. (And no, anyone who cites Discord for architectural direction
doesn't count for being morons.)

Related:

* <https://twitter.com/astralnautss/status/1500593711188787202>
* Ken Thompson "On Trusting Trust"

    #rust #security #coding
